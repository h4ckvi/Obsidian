---

database-plugin: basic

---

```yaml:dbfolder
name: Vocabulario inglés
description: new description
columns:
  __file__:
    key: __file__
    id: __file__
    input: markdown
    label: File
    accessorKey: __file__
    isMetadata: true
    skipPersist: false
    isDragDisabled: false
    csvCandidate: true
    position: 1
    isHidden: false
    sortIndex: 1
    isSorted: true
    isSortedDesc: false
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: true
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  significado:
    input: text
    accessorKey: significado
    key: significado
    id: significado
    label: significado
    position: 2
    skipPersist: false
    isHidden: false
    sortIndex: -1
    width: 267
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      wrap_content: true
  significado_2:
    input: text
    accessorKey: significado_2
    key: significado_2
    id: significado_2
    label: significado_2
    position: 3
    skipPersist: false
    isHidden: false
    sortIndex: -1
    width: 221
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  relacion:
    input: relation
    accessorKey: relacion
    key: relacion
    id: relacion
    label: relacion
    position: 4
    skipPersist: false
    isHidden: false
    sortIndex: -1
    width: 231
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: true
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      related_note_path: Home/Hábitos/Inglés/Vocabulario.md
      bidirectional_relation: true
      relation_color: hsl(211,48%,42%)
  categoría_gramatical:
    input: select
    accessorKey: categoría_gramatical
    key: categoría_gramatical
    id: categoría_gramatical
    label: categoría_gramatical
    position: 5
    skipPersist: false
    isHidden: false
    sortIndex: 2
    width: 99
    isSorted: true
    isSortedDesc: false
    options:
      - { label: "sustantivo", value: "sustantivo", color: "hsl(203, 95%, 90%)"}
      - { label: "verbo_regular", value: "verbo_regular", color: "hsl(85, 95%, 90%)"}
      - { label: "verbo_irregular", value: "verbo_irregular", color: "hsl(243, 95%, 90%)"}
      - { label: "preposición", value: "preposición", color: "hsl(132, 95%, 90%)"}
      - { label: "adjetivo", value: "adjetivo", color: "hsl(303, 95%, 90%)"}
      - { label: "adverbio", value: "adverbio", color: "hsl(349, 95%, 90%)"}
      - { label: "conjugación", value: "conjugación", color: "hsl(28, 95%, 90%)"}
      - { label: "pronombre", value: "pronombre", color: "hsl(303, 95%, 90%)"}
      - { label: "phrasal_verb", value: "phrasal_verb", color: "hsl(108, 95%, 90%)"}
      - { label: "Modal", value: "Modal", color: "hsl(323, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      option_source: manual
      content_alignment: text-align-center
      content_vertical_alignment: align-middle
config:
  remove_field_when_delete_column: false
  cell_size: normal
  sticky_first_column: false
  group_folder_column: 
  remove_empty_folders: false
  automatically_group_files: false
  hoist_files_with_empty_attributes: true
  show_metadata_created: false
  show_metadata_modified: false
  show_metadata_tasks: false
  show_metadata_inlinks: false
  show_metadata_outlinks: false
  show_metadata_tags: false
  source_data: tag
  source_form_result: "#vocabulario"
  source_destination_path: Personal/Home/Inglés/Vocabulario
  row_templates_folder: Plantillas/Plantillas A
  current_row_template: 999 - PLANTILLAS/tp.vocabulario_ingles.md
  pagination_size: 20
  font_size: 16
  enable_js_formulas: false
  formula_folder_path: /
  inline_default: false
  inline_new_position: last_field
  date_format: yyyy-MM-dd
  datetime_format: "yyyy-MM-dd HH:mm:ss"
  metadata_date_format: "yyyy-MM-dd HH:mm:ss"
  enable_footer: true
  implementation: default
filters:
  enabled: false
  conditions:
```