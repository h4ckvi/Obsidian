---
aliases:
  - API
  - Peticiones API en python
tags:
  - Programación
categoria:
  - APIs y peticiones
subcategoria: 
nivel:
  - principiante
---

# Comenzando sin dependencias

Primero, vamos a utilizar el módulo `urllib.request` que forma parte de la biblioteca estándar de Python. Con este módulo, podrás abrir URLs y manejar las respuestas de la API de forma manual.

##  Ejemplo Básico Sin Dependencias

Aquí te muestro cómo hacer una petición simple a una API:

Uso básico de urllib.request

```python
import urllib.request
import json
nurl = 'https://jsonplaceholder.typicode.com/posts/1'

response = urllib.request.urlopen(url)
data = response.read().decode('utf-8')
json_data = json.loads(data)
print(json_data)

response.close()
```

## Manejo de Respuestas JSON

Después de recibir la respuesta, es crucial transformarla desde el formato binario a un objeto JSON. En el ejemplo anterior, lo hacemos con `json.loads()` tras decodificar la respuesta.

### Importancia del Control de Errores

Es recomendable envolver el código en un bloque `try-except` para manejar posibles errores durante la petición. Esto previene que tu programa se rompa en caso de que la URL sea incorrecta o haya otros problemas:

Manejo de Errores

```python
try:
	response = urllib.request.urlopen(url)
except urllib.error.HTTPError as e:
	    print(f'Error en la solicitud: {e.code}')
except urllib.error.URLError as e:
	    print(f'Error en la URL: {e.reason}')
```

# Ahora Con Dependencias

Después de entender cómo funcionan las peticiones sin una biblioteca externa, es momento de ver cómo **simplificar este proceso** con herramientas como `requests`. Esta biblioteca hace que trabajar con APIs sea mucho más **sencillo y legible**.

## Instalando requests

Para usar `requests`, primero necesitas instalarlo. Utiliza el siguiente comando en tu consola:

Instalación de Requests

```python
pip install requests
```

## Realizando Peticiones con Requests

Una vez instalada la biblioteca, hacer peticiones se convierte en un proceso directo:

Uso de requests para una solicitud GET

```python
import requests
response = requests.get('https://jsonplaceholder.typicode.com/posts/1')
json_data = response.json()

print(json_data)
```


# Haciendo Peticiones a una API

En esta lección, **exploramos cómo hacer peticiones a una API** utilizando Python.

## Peticiones Nativas vs Con Dependencias

Comenzamos aprendiendo a hacer una petición **nativa**, que si bien es **verboza** y propensa a errores, es esencial entenderla para solucionar problemas con dependencias más adelante.

Ahora, ¿qué tal si utilizamos una librería sencilla y popular? Te presento `requests`, que simplifica notablemente este proceso.

### Instalación de `requests`

Antes de comenzar, asegúrate de tener la librería `requests` instalada. Puedes hacerlo utilizando `pip`, el gestor de paquetes de Python:

Instalación de Requests

```python
pip install requests
```

### Realizando una Petición con `requests`

Veamos cómo se hace una petición GET utilizando `requests`. Aquí un ejemplo básico:

Haciendo una Petición GET

```python
import requests
response = requests.get('https://jsonplaceholder.typicode.com/posts')
print(response.json())
```

En este ejemplo, simplemente importamos `requests`, hacemos una petición a una API y procesamos la respuesta en formato JSON.

### Accediendo a los Datos

Una vez que tenemos la respuesta JSON, podemos acceder a datos específicos de la siguiente manera:

Accediendo a los Datos

```python
data = response.json()
first_post = data[0]
print(first_post['title'])
```

Aquí, accedemos al primer post de la lista y mostramos su título.

## Reflexión Final

Hacer **peticiones a APIs** puede parecer complicado, pero con herramientas como `requests` se vuelve un proceso **sencillo** y **rápido**. Siempre es importante entender los conceptos subyacentes, ya que te permitirá solucionar problemas y aprovechar al máximo el potencial de Python.

# Método HTTP PULL

El **método HTTP PULL**, fundamental para **recuperar información** desde APIs. 

A diferencia de otros métodos como POST o PUT, PULL nos permite obtener datos sin modificar el recurso.

##  Realizando una Petición PULL

Para ilustrar cómo funciona el método PULL, realizaremos una solicitud a una API y analizaremos la respuesta.

Ejemplo de uso del método PULL en Python

```python
import requests

url = 'https://jsonplaceholder.typicode.com/posts/1'

response = requests.get(url)

if response.status_code == 200:
print(response.json())
else:
print(f'Error: {response.status_code}')
```

##  Análisis de la Respuesta

Cuando hacemos una solicitud PULL, es crucial estar atentos al **código de estado** de la respuesta. Un código `200` indica que la solicitud fue exitosa. Si no, podemos usar este código para manejar errores y realizar acciones adecuadas.

Al experimentar con APIs, aunque nuestras pruebas no guarden datos en la base de datos, nos permitirán verificar el correcto funcionamiento de nuestras solicitudes.

##  Manejo de Errores

Es importante proteger nuestras solicitudes contra errores inesperados. Puedes envolver tu código en un bloque `try-except` para manejar excepciones:

Manejo de errores en peticiones PULL

```python
import requests

try:
response = requests.get(url)
response.raise_for_status()  # Lanza una excepción para códigos de error
print(response.json())
except requests.exceptions.RequestException as e:
print(f'Ocurrió un error: {e}')
```

En esta lección, hemos aprendido los fundamentos del método HTTP PULL, cómo implementarlo en Python y gestionar adecuadamente las respuestas y errores. ¡Practica en tu propia API y desata el poder de la información!

#  Método HTTP POST

El **método HTTP POST**. Este método se utiliza para enviar datos al servidor, ideal para crear recursos o actualizar información.

##  Envío de Datos con POST

Al utilizar POST, es fundamental estructurar adecuadamente la solicitud para garantizar que los datos se envíen correctamente. Aquí te mostramos un ejemplo práctico:

Ejemplo de Solicitud POST en Python

```python
import requests

url = 'http://ejemplo.com/api/recurso'
data = {'nombre': 'valor'}

response = requests.post(url, json=data)
print(response.status_code)  # Debería imprimir 200 si la solicitud fue exitosa
```

##  Comparación con otros Métodos

Es importante entender que el método **PUT** se emplea para **actualizar** recursos existentes, mientras que **DELETE** se utiliza para eliminarlos. La estructura de las solicitudes es similar, pero la intención de cada método varía.

##  Análisis de Respuestas

Siempre es recomendable manejar las respuestas del servidor. Puedes encontrarte con diferentes códigos de estado HTTP que indican el resultado de tu solicitud. Por ejemplo, un código `404` indica que el recurso no existe, lo que es común si intentas acceder a un recurso inexistente.

¡Prepárate para poner en práctica lo que aprendes en esta lección y lleva tus habilidades de programación en Python al siguiente nivel!

# PATCH vs PUT: ¿Cuál usar?

Depende de si necesitas realizar una actualización parcial o completa del objeto.

##  ¿Qué es PUT?

El método **PUT** se utiliza para enviar un objeto completo para ser actualizado. Esto significa que debes pasar todos los campos del objeto, incluso aquellos que no han cambiado.

### Ejemplo de uso de PUT

Un ejemplo común de uso de **PUT** podría ser el siguiente:

Ejemplo de uso de PUT

```javascript
const actualizarUsuario = async (usuario) => {
const response = await fetch('https://api.ejemplo.com/usuarios/' + usuario.id, {
method: 'PUT',
body: JSON.stringify(usuario),
headers: {
'Content-Type': 'application/json'
}
});
return response.json();
};
```

##  ¿Qué es PATCH?

Por otro lado, **PATCH** es ideal cuando solo necesitas actualizar partes específicas de un objeto. Proporciona un enfoque más eficiente, ya que solo envías los campos que realmente deseas cambiar.

### Ejemplo de uso de PATCH

Aquí tienes un ejemplo de cómo usar **PATCH** para actualizar solo el título de un objeto:

Ejemplo de uso de PATCH

```javascript
const actualizarTitulo = async (id, nuevoTitulo) => {
const response = await fetch('https://api.ejemplo.com/usuarios/' + id, {
method: 'PATCH',
body: JSON.stringify({ title: nuevoTitulo }),
headers: {
'Content-Type': 'application/json'
}
});
return response.json();
};
```

##  Conclusión

Recuerda, **PATCH** es más eficiente y fiable para actualizaciones parciales, mientras que **PUT** está diseñado para la actualización completa de un recurso. Al elegir entre estos dos métodos, piensa en la cantidad de datos que realmente necesitas enviar y opta por la opción que minimiza la posibilidad de errores y facilita la mantenibilidad de tu aplicación. ¡Practica con estos métodos en tus proyectos y mejora tus habilidades en el manejo de APIs!

# Método HTTP Query

El método QUERY es una innovadora forma de realizar peticiones HTTP que facilita la **interacción** con APIs. Mientras que el método GET tiene limitaciones para enviar datos en el cuerpo de la petición, el método QUERY permite incluir un **JSON** al hacer la solicitud, lo que simplifica la transmisión de datos complejos.

## Ejemplo de uso de QUERY

Muchas veces, al trabajar con APIs, es necesario limitar el número de resultados o buscar elementos específicos. Con el método QUERY puedes hacer esto de forma más sencilla. A continuación, te presentamos un ejemplo de cómo se podría implementar:

Ejemplo de consulta con QUERY

```python
import requests

url = 'https://api.example.com/posts'
query_params = {
'limit': 5,
'search': 'producto'
}

response = requests.get(url, params=query_params)
data = response.json()
print(data)
```

## 🛠️ ¿Por qué usar el método QUERY?

Los **query params** a menudo son complicados, especialmente al pasar arrays. Con el método QUERY, enviar un array como parte de tu JSON es mucho más fácil y claro. Esto es crucial cuando te enfrentas a situaciones en las que los datos son complejos o cuando necesitas mayor claridad en la transmisión de información.

## Beneficios clave:

1. **Simplicidad** al transmitir datos.
2. **Facilidad** para manejar estructuras complejas como arrays.
3. **Mejor mantenimiento** de la API y del código.

Con el método QUERY, ¡tu vida como desarrollador Python será mucho más sencilla y efectiva!

# Integrando la API de OpenAI en Python

En esta lección, aprenderás a **utilizar la API de OpenAI** sin la necesidad de instalar un SDK o dependencias adicionales. Te guiaré a través de los pasos necesarios para hacer peticiones manuales y recibir respuestas de la API.

## 🚀 ¡Comencemos!

### ¿Qué necesitas?

Primero, asegúrate de tener tu **API key**. Para obtenerla, ve a los ajustes de tu cuenta en OpenAI, donde podrás generar una nueva clave secreta.

Cómo obtener tu API Key

```python
// Obtención de la API Key\n\n// Acceder a 'Settings' y crear una nueva API Key\n\n// Guarda tu API Key en un lugar seguro.
```

### 📡 Realizando peticiones

Para interactuar con la API de OpenAI, necesitaremos definir la URL y los headers necesarios, incluyendo nuestra API key. A continuación, creamos la función para realizar la solicitud.

Ejemplo de función para realizar la solicitud

```python
import requests\n\ndef call_openai(api_key, prompt):\n    url = 'https://api.openai.com/v1/chat/completions'\n    headers = {\n        'Content-Type': 'application/json',\n        'Authorization': f'Bearer {api_key}'\n    }\n    data = {\n        'model': 'gpt-3.5-turbo',\n        'messages': [{'role': 'user', 'content': prompt}]\n    }\n    response = requests.post(url, headers=headers, json=data)\n    return response.json()
```

#### 📝 Pasando el **prompt**

En la función anterior, pasaremos el **prompt** que deseamos enviar a la API. En este caso, podemos pedirle a OpenAI que escriba un poema sobre programación.

### 🔍 Análisis de la respuesta

Después de realizar la petición, podremos analizar la respuesta que obtendremos. La respuesta incluirá varios elementos, y puedes acceder a la información relevante haciendo lo siguiente:

Obtención y uso de la respuesta

```python
result = call_openai(api_key, 'Escribe un poema sobre la programación')\n\n# Procesar la respuesta\nprint(result)
```

Ahora que tienes una estructura básica para trabajar con la API de OpenAI, puedes experimentar con diferentes prompts y modelos disponibles.

### 🎯 Conclusiones

En esta lección, aprendiste a integrar la API de OpenAI en un entorno de Python sin dependencias adicionales. Ahora, puedes expandir tus proyectos utilizando las capacidades de inteligencia artificial de OpenAI. ¡A seguir practicando!


# 🌟 Interactuando con la API de OpenAI

En esta lección, aprenderás a utilizar la API de OpenAI en **Python** y a manejar las respuestas que obtienes en formato **JSON**. Este aprendizaje es crucial para integrar potentes modelos de generación de texto en tus aplicaciones.

## 🛠️ Comenzando con la API

Lo primero que haremos es hacer una **petición** a la API de OpenAI y guardar la respuesta en una variable. Utilizaremos la función `response.json()` para obtener los datos en formato JSON que luego podemos manipular.

Ejemplo de petición a la API

```python
import requests

url = 'https://api.openai.com/v1/endpoint'  # Asegúrate de reemplazar con el endpoint correcto
headers = {
'Authorization': 'Bearer tu_api_key',
}

response = requests.get(url, headers=headers)
APIResponse = response.json()
```

## 📊 Manejo de la Respuesta JSON

Una vez que tenemos la `APIResponse`, podemos utilizar un método útil llamado **dumps** para imprimir la respuesta de forma más legible. Esto facilita la visualización de la estructura de los datos recibidos.

Asegúrate de que no haya conflicto de nombres entre tus variables y los módulos importados, ya que esto puede generar confusiones en tu código.

Imprimir la respuesta en formato legible

```python
import json

pretty_response = json.dumps(APIResponse, indent=2)
print(pretty_response)
```

## 🎉 Creando Respuestas Bonitas

Con la estructura JSON clara, puedes extraer información específica de la respuesta. Por ejemplo, si deseas mostrar el contenido del mensaje que recibiste, puedes realizar lo siguiente:

Acceso al contenido del mensaje

```python
message_content = APIResponse['choices'][0]['message']['content']
print(message_content)
```

Así, en lugar de recibir un montón de datos, obtendrás solo lo que necesitas para presentar la información de manera más atractiva. ¡Inténtalo y disfruta de la potencia de la IA en tus proyectos de Python!
