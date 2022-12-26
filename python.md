# probar api con python

 ##requests - Hacer peticiones http en Python

requests es una librería Python que facilita enormemente el trabajo con
peticiones HTTP. Puede ser utilizada para hacer peticiones a una api.

## Instalación

Al tratarse de una librería de terceros, lo primero que debes hacer es
instalarla. Lo más fácil para ello, es utilizar el gestor de paquetes pip:

<::before>1.

$> pip install requests

## Cómo hacer una petición GET en Python con requests

Una de las operaciones más habituales con la librería requests es hacer una
petición GET, ya sea para obtener el contenido de una web o para realizar una
petición a un API.

Para ello, simplemente tienes que invocar a la función get() indicando la URL
a la que hacer la petición.

<::before>1.

import requests

<::before>2.

<::before>3.

resp = requests.get('https://www.google.com/')

La función devuelve un objeto Response, que en este caso se ha asignado a la
variable resp, con toda la información de la respuesta.

## Cómo hacer una petición POST en Python con requests

Si quieres hacer una petición POST, es lo mismo solo que debes llamar a la función post() e indicar en el parámetro data un diccionario con los datos del cuerpo de la petición. requests se encarga de codificarlos correctamente antes de
realizar la petición:

<::before>1.

import requests

<::before>2.

<::before>3.

auth_data = {'email': 'juanjo@j2logo.com', 'pass': '1234'}

<::before>4.

resp = requests.post('https://mipagina.xyz/login/', data=auth_data)

para mandar datos multivaluados, se
pueden especificar los diferentes valores de dos maneras distintas.

En un diccionario, indicando una lista de valores para una clave:

<::before>1.

import requests

<::before>2.

<::before>3.

form_data = {'color': ['blanco', 'verde'], 'idioma': 'es'}

<::before>4.

resp = requests.post('http://mipagina.xyz/formulario/', data=form_data)

O como una lista de tuplas:

<::before>1.

import requests

<::before>2.

<::before>3.

form_data = [('color', 'blanco'), ('color', 'verde'), ('idioma', 'es')]

<::before>4.

resp = requests.post('http://mipagina.xyz/formulario/', data=form_data)

## El resto de peticiones con requests

Del mismo modo que existen las funciones get() y post(), requests tiene
funciones para los siguientes métodos de petición: PATCH, PUT, DELETE, HEAD y
OPTIONS. Son patch(), put(), delete(), head() y options().



## El objeto Response. Respuesta de la petición

Una vez que hemos repasado los aspectos principales para realizar una petición
HTTP, en esta sección nos vamos a centrar en el objeto Response, que se
obtiene como resultado de una petición.

Este objeto contiene toda la información referente a la respuesta, como el
contenido, el código de respuesta, las cabeceras o las cookies.

### Contenido de la respuesta

Cuando la respuesta que devuelve un servidor es de tipo texto, por ejemplo
html o xml, el contenido se encuentra en el atributo text del objeto Response.

requests automáticamente decodifica el contenido devuelto por el servidor,
adivinando la codificación a emplear a partir de las cabeceras de la
respuesta. Para conocer la codificación empleada puedes acceder al atributo
encoding.

<::before>1.

>>>import requests

<::before>2.

<::before>3.

<::before>

r.encoding

<::before>

'ISO-8859-1'

<::before>6.

r.text

<::before>7.

Para aquellos casos en los que la respuesta no es texto, como por ejemplo una
imagen o un pdf, entonces se debe acceder al atributo , ya que este devuelve
el contenido como una secuencia de bytes.

<::before>

# código que maneja la secuencia de bytes descargada

### Código de estado de la respuesta

<::before>1.

<::before>2.

<::before>3.

<::before>4.

<::before>5.

200

### Cabeceras de la respuesta

Las cabeceras de la respuesta están accesibles a través del atributo headers.
Este atributo es un diccionario especial que contiene cada una de las
cabeceras devueltas como claves del diccionario.

## Cómo pasar parámetros en la URL en Python con requests

En ocasiones es necesario pasar una serie de parámetros en la URL de la
petición. Esto se puede hacer de forma manual añadiendo a la URL una cadena
que comienza por el carácter ? seguido de pares de la forma
parm1=valor1&param2=valor2....

Por ejemplo:

<::before>

import requests

<::before>

<::before>3.

<::before>.

r = requests.get('http://unblog.xyz', params=parametros)

## Peticiones y respuestas JSON en Python con requests

Uno de los usos más habituales de la librería requests es hacer peticiones a
un API desde una aplicación.

A continuación, te mostraré lo fácil que es hacer llamadas a un API utilizando
la librería requests.

### Python GET requests

Si la respuesta es un JSON, que es lo más común, podemos llamar al método
json() de la respuesta para que decodifique los datos y los devuelva como un
diccionario con los campos de dicho JSON.

### Python POST requests

<::before>1.

import requests

<::before>3.

<::before>4.

[fuente](https://j2logo.com/python/python-requests-peticiones-http/)