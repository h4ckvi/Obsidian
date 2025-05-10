<%*
const file = await app.vault.read(app.workspace.getActiveFile());
let lines = file.split('\n');

let inCodeBlock = false;
let count = [0, 0, 0];
let toc = "# Índice\n\n";
let updatedLines = [];

let inYAML = false;
let yamlEndLine = -1;

// Detectar si hay frontmatter y encontrar su final
if (lines[0].trim() === "---") {
  inYAML = true;
  for (let i = 1; i < lines.length; i++) {
    if (lines[i].trim() === "---") {
      yamlEndLine = i;
      break;
    }
  }
}

// Procesar encabezados numerados
for (let i = 0; i < lines.length; i++) {
  let line = lines[i];
  if (line.trim().startsWith("```")) inCodeBlock = !inCodeBlock;

  const match = !inCodeBlock && line.match(/^(#{1,3})\s+(.*)/);
  if (match) {
    const level = match[1].length;
    let title = match[2].trim();

    const existingNumbering = title.match(/^(\d+\.)+ /);
    if (existingNumbering) {
      title = title.replace(/^(\d+\.)+ /, '');
    }

    count[level - 1]++;
    for (let j = level; j < 3; j++) count[j] = 0;
    const numbering = count.slice(0, level).join(".");

    toc += `${"  ".repeat(level - 1)}- [[#${numbering}. ${title}]]\n`;
    line = `${"#".repeat(level)} ${numbering}. ${title}`;
  }

  updatedLines.push(line);
}

// Construir bloque del índice
const tocBlock = `<!--INDICE-->\n${toc}<!--/INDICE-->`;

// Insertar o reemplazar índice
let updatedFile;

if (file.includes("<!--INDICE-->") && file.includes("<!--/INDICE-->")) {
  updatedFile = updatedLines.join('\n').replace(/<!--INDICE-->[\s\S]*?<!--\/INDICE-->/g, tocBlock);
} else if (inYAML && yamlEndLine !== -1) {
  const before = updatedLines.slice(0, yamlEndLine + 1).join('\n');
  const after = updatedLines.slice(yamlEndLine + 1).join('\n');
  updatedFile = `${before}\n\n${tocBlock}\n\n${after}`;
} else {
  updatedFile = `${tocBlock}\n\n${updatedLines.join('\n')}`;
}

await app.vault.modify(app.workspace.getActiveFile(), updatedFile);
%>