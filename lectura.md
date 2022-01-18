Lectura

Unidad: AJAX (UJS)
------------------------

**Descripción:**

En esta unidad aprenderemos las siguientes competencias:

> - Conocer librería UJS y por qué se encuentra
incluida en Rails.
> - Comprender flujo de trabajo de AJAX en
Rails.
> - Manipular el DOM como respuesta a una
petición AJAX asociada a un recurso.
> - Manipular recursos utilizando AJAX:
modales y formularios.

La gema "rails-ujs" es importante ya que la funcionalidad que provee es muy útil al momento de desarollar un proyecto y el intentar implementar estas funcionalidades por nuestra cuenta no es fácil y podríamos llegar a un resultado no tan bueno como el de la gema misma. Esta gema fue integrada a Rails en la versión 5 dada su gran utilidad. Además aprenderemos que son las llamadas AJAX y porque son tan importantes. En pocas palabras estas son llamadas HTTP que se realizan de forma asíncrona al servidor, lo que permite traer o enviar información al servidor, sin recargar la página, de forma rápida y así entregar una buena experiencia de navegación al usuario.

### Requerimientos

> - Editor de texto de preferencia
> - Tener Ruby instalado, versión 2.2.10 o superior
> - Tener Rails instalado, versión 5.1 o superior
> - Conocer el flujo completo de un request HTTP
> - Conocer los diversos métodos HTTP que puede tener un request/llamada
> - Conocer la diferencia entre una llamada GET y una llamada POST
> - Saber lo que significa CRUD
> - Conocimiento basico de modelos de ActiveRecord
> - Conocimientos basicos de JavaScript

### Referencias
> - [https://github.com/rails/rails-ujs/tree/master](https://github.com/rails/rails-ujs/tree/master)
> - [https://www.w3schools.com](https://www.w3schools.com)
> - https://www.aprenderaprogramar.com/index.php?option=com_content&view=article&id=882
> - https://coffeescript.org/#language
> - [https://thoughtbot.com/blog/a-tour-of-rails-jquery-ujs](https://thoughtbot.com/blog/a-tour-of-rails-jquery-ujs)

### Glosario
**HTTP**: Hypertext Transfer Protocol, es el protocolo de transferencia de datos usado por la World Wide Web (www)

**GET**: Las peticiones HTTP tienen métodos, los cuales determinan como se maneja la petición, el método GET, solicita un recurso, debe utilizarse para obtener datos y no debe tener ningún otro efecto.

**POST**: Es el método que se utiliza para enviar datos al servidor.

**AJAX**: Asynchronous JavaScript and XML, es un grupo de tecnologías que permite realizar llamadas HTTP de forma asíncrona al servidor, lo que da dinamismo a la pagina porque permite una comunicación cliente/servidor sin recargar o cambiar la página en la que se encuentra el cliente

**CRUD**:

**ActiveRecord**: El el ORM de Ruby on Rails, el cual nos permite interactuar con la base de datos de nuestro proyecto a través de "Modelos", que son simplemente clases de Ruby pero que representan una tabla en la base de datos.

**Modelo**: Es una clase de Ruby que representa una tabla de la base de datos y puede interactuar con esta por medio del ORM de Rails, Active Record

**Llamada/request**: Es una petición HTTP que realiza el usuario/cliente navegando o interactuando con un sitio web o dirección URL, está petición sera procesada por el servidor que mantiene el sitio web activo.

**Respuesta/response**: Es lo que envía el servidor al usuario/cliente después procesar su petición.

**rails-ujs**: Es una librería de Javascript no intrusivo, esto implica que intenta seguir un conjunto de buenas practicas y además intenta separar la capa de comportamiento de las etiquetas HTML

**XML**: XML es un lenguaje de marcado similar a HTML. Significa Extensible Markup Language (Lenguaje de Marcado Extensible) y es una especificación de W3C como lenguaje de marcado de propósito general. Esto significa que, a diferencia de otros lenguajes de marcado, XML no está predefinido, por lo que debes definir tus propias etiquetas. El propósito principal del lenguaje es compartir datos a través de diferentes sistemas, como Internet.

**DOM**: Document Object Model, cuando se carga una pagina web se crea un DOM de ella. El DOM HTML es un modelo estándar  de objetos y una interfaz de programación para HTML. Define los siguientes cuatro aspectos:

- Los elementos HTML como objectos
- Las propiedades de todos los objectos HTML
- Los métodos para acceder a todos los objectos HTML
- Los eventos de todos los elementos HTML

En otras palabras: El DOM HTML es un estándar de como obtener, cambiar, agregar, o borrar elementos HTML.

**jQuery**: Es una biblioteca multiplataforma de JavaScript, creada inicialmente por John Resig, que permite simplificar la manera de interactuar con los documentos HTML, manipular el árbol DOM, manejar eventos, desarrollar animaciones y agregar interacción con la técnica AJAX a páginas web

**CoffeeScript**: Es un lenguaje de programación que se compila a JavaScript. El lenguaje añade azúcar sintáctico inspirado en Ruby, Python y Haskell2​ para mejorar la brevedad y la legibilidad de JavaScript, y añade características más sofisticadas, como la comprensión de listas y la coincidencia de patrones.

**Helpers**: Son métodos auxiliares que provee Rails con el fin de facilitar el trabajar con assets, fechas, formularios, números entre otros.

**Controladores**: Son clases de Ruby cuyo nombre termina en Controller y extienden de la clase ActionController, son los archivos responsables de manejar los requests del cliente, en el archivo de rutas se especifica que controlador y cual de sus métodos recibirá el request del usuario.

**Vistas**: Es la capa de presentación del modelo MVC, son archivos .html.erb en los cuales se puede escribir código Ruby, HTML e incluso JavaScript

Capitulo 1
------------------------

### ¿ Que es la librería UJS ?

#### Competencias
- Conocer la gema rails-ujs y que nos provee
- Familiarizarse con ejemplos donde se puede utilizar las funcionalidades de la gema rails-ujs

#### Motivación
La gema rails-ujs es importante puesto que a pesar de no poseer muchas funcionalidades, ya que los problemas que busca resolver, los resuelve de muy buena forma, además dado que estos problemas son tan recurrentes en los proyectos que el equipo de Ruby on Rails decidió incorporar esta gema a Rails desde las versión 5.1, lo cual recalca la importancia de conocer esta gema.

#### rails-ujs
"rails-ujs", es una librería de Javascript no intrusivo, esto implica que intenta seguir un conjunto de buenas practicas y además intenta separar la capa de comportamiento de las etiquetas HTML, logrando entre otras cosas:

- Código desacoplado.
- Código escalable.
- Código mantenible.

Está librería fuera creada para el framework Ruby on Rails pero puede usarse en otros proyectos sin problema.

 1. Fuerza dialogos (pop-up) de confirmación para varias acciones
 2. Permite hacer request que no sean GET desde los hipervinculos
 3. Permite que formularios e hipervinculos suban información asincronamente con Ajax
 4. Hace que los botones para subir los formularios se desactiven automáticamente después de apretarlos para evitar prevenir el clickearlos dos veces

Estas funcionalidades se pueden lograr agregando ciertos atributos "data-" al HTML. En Rails estos son agregados por el template del framework.

Fue incluida en Rails 5.1 ya que es una gema muy usada y la funcionalidad que provee se estimo lo suficientemente importante para incorporarla dentro del framework mismo.

**Ejemplos de uso de cada una de las funcionalidades de ujs**

 1. Dialogos de confirmación
 ```ruby
 <%= form_for item, data: { confirm: 'Are you sure?' } %>
 ```

 2. Requests que no sean GET desde los hipervinculos
 ```ruby
 <%= link_to 'Delete', item, method: :delete %>
 ```
 3. Que los formularios y links envien información al server usando el metodo POST
```ruby
<%= form_for item, remote: true %>
```
 4. Evitar doble envio de información con los botones submit
```ruby
<%= form.submit data: { disable_with: 'Submitting...' } %>
```

Capitulo 2
------------------------

### ¿ Que es AJAX ?

#### Competencias
- Conocer que es AJAX y como utilizarlo
- Que es el DOM y como se puede modificar utilizando llamadas AJAX
- Los pro y los contra del uso de AJAX

#### Motivación

AJAX, acrónimo de Asynchronous JavaScript And XML (JavaScript asíncrono y XML), es una técnica de desarrollo web para crear aplicaciones interactivas o RIA (Rich Internet Applications). Estas aplicaciones se ejecutan en el cliente, es decir, en el navegador de los usuarios mientras se mantiene la comunicación asíncrona con el servidor en segundo plano.

De esta forma es posible realizar cambios sobre las páginas sin necesidad de recargarlas, mejorando la interactividad, velocidad y usabilidad en las aplicaciones.

#### AJAX

AJAX es una tecnología asíncrona, en el sentido de que los datos adicionales se solicitan al servidor y se cargan en segundo plano sin interferir con la visualización ni el comportamiento de la página, aunque existe la posibilidad de configurar las peticiones como síncronas de tal forma que la interactividad de la página se detiene hasta la espera de la respuesta por parte del servidor.

Por ejemplo usualmente en paginas Chilenas, los selectores de comunas que dependen de un selector de Región, funcionan con Ajax, porque dependiendo de la región escogida le piden al servidor las comunas asociadas.

Todo tipo de manipulaciones del DOM que se pueden hacer con AJAX.

#### ¿Recuerdan que es el DOM ?

Document Object Model, cuando una pagina web carga, el browser crea un Document Object Model de la pagina.

El DOM HTML es construido como un árbol de objetos con el objeto/tag <html> como raiz.

##### Manipulaciones del DOM

Usando AJAX es prácticamente posible realizar cualquier tipo de modificación que se desee al DOM, ya que cuando uno hace un llamado Ajax, uno puede escribir una función callback con código a ejecutar cuando el server responda y en esa función se puede escribir lo que uno desee.

**Por ejemplo:**

 - A una tabla se le pueden pedir los datos usando Ajax
 - A una tabla o lista paginada se le pueden pedir los datos de las
   otras paginas usando Ajax para no tener que recargar el resto de la
   pagina
 - Se pueden traer los datos para mostrar un gráfico usando Ajax.
etc...


#### Beneficios de AJAX
a) No es necesario recargar la página web completa cada vez que se necesite algún dato del servidor, con lo que todo es más rápido.

b) El usuario no percibe que haya demoras: está trabajando y al ser las comunicaciones en segundo plano no hay interrupciones. Esto tiene que ser acompañado con "loaders" donde corresponda para que el usuario sepa que hay información/datos pendientes.

c) Los pasos que antes podía ser necesario dar cargando varias páginas web pueden quedar condensados en una sola página que va cambiando gracias a AJAX y a la información recibida del servidor. Por ejemplo procesos de registro largos.

#### Posibles problemas con AJAX

a) El usuario puede perder la capacidad para hacer cosas que hacía con webs tradicionales puesto que no hay cambio de página web. Por ejemplo usar los botones de avance y retroceso del navegador o añadir una página a favoritos puede dejar de ser posible. Esto en algunos casos no es deseable.

b) El desarrollo de aplicaciones web se puede volver más complejo. Supongamos que antes tuviéramos un proceso en el que avanzábamos a través de varias páginas web como 1, 2, 3. De este modo la organización resulta sencilla. Si condensamos todo en una sola página web: 1, escribir y depurar el código puede volverse más complicado. En sitios complejos, puede ser muy difícil depurar errores.

c) Existen problemas y restricciones de seguridad relacionados con el uso de Ajax. Hay que tener en cuenta que por motivos de seguridad no todos los procesos se pueden realizar del lado del cliente (que por su propia naturaleza es “manipulable”). También existen restricciones de seguridad para impedir la carga de contenidos mediante Ajax desde sitios de terceras partes.

d) La indexación para los motores de búsqueda se ve dificultada, con lo cual nuestros sitios web pueden perder visibilidad en los buscadores. No es lo mismo un contenido “constante” o aproximadamente estático, fácilmente rastreable para un buscador, que un contenido “cambiante” en función de la ejecución de JavaScript, difícilmente rastreable para un buscador.

**Llamadas de AJAX anidadas**

Hay veces en las que hay que hacer llamadas de Ajax anidadas, por ejemplo cuando uno habla de una dirección, puede seleccionar un país, cuando lo seleccione se hace Ajax para traer las regiones asociadas a ese país, luego cuando ese request se completa exitosamente hay que hacer otro llamado Ajax dentro del anterior, para traer las comunas asociadas a la región.

Pero hay que intentar mantener las llamadas anidadas al mínimo ya que hacen que el código sea mas complejo y en muchas ocasiones no se manejan bien todos los posibles resultados de las llamadas, lo cual puede generar errores inesperados. Para saber más de los problemas que esto puede traer se puede buscar **Callback Hell**.

**Ejemplo muy simple de llamadas AJAX anidadas**
```javascript
$.ajax({
    url: "http://example.com",
    complete: function() {
        console.log("STOP");
        $.ajax({
            url: "http://example.com",
            complete: function() {
                console.log("THIS");
                $.ajax({
                    url: "http://example.com",
                    complete: function() {
                        console.log("MAD");
                        $.ajax({
                            url: "http://example.com",
                            complete: function() {
                                console.log("MAN!");
                            }
                        })
                    }
                })
            }
        })
    }
})
```
Capítulo 3
------------------------
### AJAX usando rails-ujs

#### Competencias
- Ejemplos concretos de llamadas AJAX y de las diversas formas en que se pueden realizar
- Que es coffeeScript y cual es su utilidad frente al Javascript tradicional
- Los helpers de Rails que se pueden configurar para que realicen llamadas con AJAX
- Los momentos en el flujo de una llamada AJAX en los que puede gatillarse código

#### Motivación

En este capítulo veremos ejemplos concretos de como hacer llamadas AJAX sin rails-ujs, luego usando rails-ujs y también los helpers que nos proporciona Rails para hacerlo de la forma mas limpia posible y con la menor cantidad posible de código. Todo esto es muy importante ya que es como realmente usaremos AJAX en nuestros proyectos

#### Ejemplos

Ejemplo de cómo hacer una llamada ajax con rails-ujs y coffee script
```coffeescript
$.ajax(url: "/test").done (html) ->
  $("#results").append html
```
Llamada ajax usando jQuery
```javascript
$.ajax({
  type: "POST",
  url: "/things",
  data: mydata,
  success: function(data, textStatus, jqXHR){...},
  error: function(jqXHR, textStatus, errorThrown){...}
})
```
Como se puede apreciar, ambas formas sirven para realizar una llamada ajax al servidor, pero cada una tiene ventajas y desventajas:

#### Ventajas de la llamada usando coffee script:

 - El código queda más ordenado porque se tiene que escribir en un
   archivo aparte de tipo coffee script
 - Es menor cantidad de código, menos verboso

#### Desventajas de la llamada usando coffee script:

 - Las opciones de la llamada no son tan evidentes como en el caso de la
   llamada con jQuery.

#### Ventajas de la llamada con jQuery

 - Es una llamada simple y con las opciones explícitas por lo que es
   fácil de utilizar
 - Se puede colocar en el mismo archivo .html.erb de las vistas o en un
   archivo .js aparte, aunque lo recomendado es dejarlo en otro archivo.
 - Hay muchos ejemplos disponibles de distintos tipos de llamada en la
   web

#### Desventajas de la llamada con jQuery

 - El código es verboso y más grande comparado con su contraparte en
   Coffe script

Ahora veremos como Rails nos permite realizar llamadas ajax, de forma simple, desde los formularios usando helpers para vistas que funcionan por medio del atributo data-remote

#### form_with
form_with es uno de los helpers que provee Rails para construir formularios. Por defecto, form_with asume que se quiere ocupar ajax para enviar la información del formulario. Este comportamiento se puede cambiar utilizando la opción :local del helper form_with.

```ruby
<%= form_with(model: @article) do |f| %>
  ...
<% end %>
```
Esto genera el siguiente código html

```ruby
<form action="/articles" accept-charset="UTF-8" method="post" data-remote="true">
  ...
</form>
```

Ahora que el formulario tiene **data-remote="true", será enviado por Ajax**. Para agregar una acción, cuando dicha llamada sea exitosa o falle, hay que agregar código como el siguiente:
```coffeescript
$(document).ready ->
  $("#new_article").on("ajax:success", (event) ->
    [data, status, xhr] = event.detail
    $("#new_article").append xhr.responseText
  ).on "ajax:error", (event) ->
    $("#new_article").append "<p>ERROR</p>"
```

En este código podemos apreciar que se manejan los casos cuando la llamada es exitosa (ajax:success) y también cuando la llamada falla (ajax:error) por alguna razón.

#### link_to

Es un helper que nos facilita crear hipervínculos en nuestros proyectos.

```ruby
<%= link_to "an article", @article, remote: true %>
```
Esto genera el siguiente código html

```ruby
<a href="/articles/1" data-remote="true">an article</a>
```
Aquí se puede ver que el helper link_to, permite la opción remote, la que dándole el valor true hace que la llamada se realice con Ajax.

**Otro ejemplo**
```ruby
<%= link_to "Delete article", @article, remote: true, method: :delete %>
```
Un extracto de código coffee script que se podría ocupar para manejar esta llamada Ajax, podría ser de la siguiente forma:
```coffeescript
$ ->
  $("a[data-remote]").on "ajax:success", (event) ->
    alert "The article was deleted."
```
En este caso vemos que el manejo de la llamada Ajax es simplemente lanzar un "alert" que indica que el artículo sobre el que se realizó la "acción de borrar" fue borrado exitosamente.

#### button_to
El helper button_to nos permite poner botones en nuestros proyectos, los que funcionan como links. La diferencia con el helper link_to es que, visualmente, genera un botón y por debajo éste es un formulario que tiene como botón de "submit" el botón solicitado. Este helper, además, permite la opción "remote" que al igual que en el caso del helper link_to, nos permite indicar que queremos realizar la llamada por medio de Ajax.
```ruby
<%= button_to "An article", @article, remote: true %>
```
Este ejemplo genera el siguiente código html

```ruby
<form action="/articles/1" class="button_to" data-remote="true" method="post">
  <input type="submit" value="An article" />
</form>
```
#### AJAX event handlers
Existen distintos "event handlers" (eventos para manejar las respuestas de las llamadas Ajax) ahora veremos sus nombres y cuándo se gatillan:

**ajax:before**
Antes de todos los Ajax que se utilicen

**ajax:beforeSend**
Justo antes de enviar la llamada Ajax

**ajax:send**
Cuando se envía la llamada Ajax

**ajax:stopped**
Cuando la llamada es detenida

**ajax:success**
Cuando se completa la llamada y es exitosa

**ajax:error**
Cuando se completa la llamada y falla

**ajax:complete**
Cuando se completa la llamada independiente de si fue exitosa o no

Capítulo 4
------------------------

### AJAX en los mantenedores

#### Competencias
- Que es el CRUD de un modelo
- Como realizar las llamadas HTTP que necesita un CRUD utilizando AJAX
- Buenas practicar para estructurar nos código al utilizar AJAX y Javascript en general

#### Motivación

Es importante saber como crear mantenedores ya que nos permiten interactuar con tablas de la base de datos sin la necesidad de tener acceso completa a esta, lo que mejora la seguridad y evita accidentes de uso. Muchas veces perfiles que no son del área de TI ni tienen conocimientos de bases de datos están acostumbrados a usar mantenedores en los proyectos para gestionarlos, por ejemplo crear nuevas categorías de algún modelo, crear alguna publicidad, etc. Con AJAX se pueden crear mantenedores fáciles de usar y que tengan buena navegabilidad para el usuario

En este capítulo veremos cómo realizar un mantenedor en Rails utilizando llamadas Ajax por medio de rails-ujs

#### CRUD

Todos los mantenedores realizan las siguientes llamadas al servidor:

- Create
- Read
- Update
- Delete

Todas estas llamadas se pueden realizar usando AJAX, una de las cosas que las diferencia es el método http que utilizan, lo cual es configurable en una llamada AJAX

Los helpers que vimos en el capítulo anterior nos permiten realizar estas acciones sobre algún modelo de nuestro proyecto. A continuación, veremos algunos ejemplos de cada uno de estas acciones utilizando rails-ujs y Ajax para las llamadas, suponiendo que tenemos un modelo llamado "Artículo".

**Ejemplos de llamadas CREATE**

```ruby
<%= form_with(model: @article) do |f| %>
  ...
<% end %>
```
```ruby
<%= button_to "An article", @article, remote: true %>
```
**Ejemplo de llamadas READ**
```ruby
<%= link_to "an article", @article, remote: true %>
```
**Ejemplo de llamada UPDATE**

```ruby
<%= form_with model: Post.first do |form| %>
  <%= form.text_field :title %>
<% end %>
```

**Ejemplo de llamada DELETE**
```ruby
<%= link_to "Delete article", @article, remote: true, method: :delete %>
```
Al realizar todas las llamadas del mantenedor utilizando Ajax, evitamos que el usuario tenga que cambiar de página para gestionar la información asociada al modelo.
Un problema de lo anterior es que el usuario, de forma muy simple, puede borrar o modificar "artículos", lo cual puede ser un problema dependiendo de la importancia del modelo que se esté administrando. Para mitigar esto, siempre hay que ocupar "diálogos de confirmación" sobre todo para las acciones de borrar y actualizar.

#### Estructura del código
Es importante estructurar de forma ordenada las llamadas que se realizan en nuestros proyectos, sobre todo las de Javascript ya que se pueden poner en diversos lugares. Un mantenedor como el anterior implica un gran número de archivos si se programa correctamente, por esto recordaremos algunas buenas prácticas a tener en consideración:

 - Dejar el código javascript asociado a las llamadas Ajax en un archivo
   aparte, formato coffee script o javascript
 - Usar helpers de vistas que nos provee Rails cada vez que sea posible
 - Crear nuestros propios helpers para vistas, en caso de necesitarlo, y
   dejarlos como helpers. No escribirlos directamente en los archivos
   .html.erb
 - Reutilización de código habitual. Como el caso típico del formulario
   para crear un nuevo "artículo" y para su edición, que comparten el
   formulario.
 - Manejar en cada llamada AJAX tanto el caso de respuesta exitosa como
   el de respuesta fallida.
 - Si una llamada AJAX demora un tiempo notorio/perceptible, utilizar
   loaders/alerts/toasters según corresponda para que el usuario sepa
   que su petición está siendo atendida y el sistema no ha fallado.

Capitulo 5
------------------------

### ¿ Porque no usar siempre AJAX ?

#### Competencias
- Conocer en que momentos siempre es recomendable usar AJAX
- Conocer cuando usar AJAX podría ser mas perjudicial que beneficioso

#### Motivación

Si bien AJAX es una muy buena herramienta, es necesario saber y entender que no siempre es recomendado usar AJAX y cuando es muy recomendado utilizarlo, así como los problemas que podría generar el usarlo siempre o de forma desmedida.

#### Experiencia de usuario vs carga del servidor
El usar Ajax para todas las llamadas que se hacen al servidor puede resultar en un gran numero de requests/peticiones, al servidor, lo que puede hacer que no responda inmediatamente o se sature lo que puede terminar en que el server se caiga o que nuestro request no obtenga respuesta.

Además es importante tener en cuenta, que hay llamados al servidor que si se tienen que hacer en cierto orden y si se realizan en la misma página no se pueden dejar con Ajax o el segundo puede terminar antes que el primero, si bien se pueden ocupar llamadas Ajax anidadas, eso no es siempre o tan recomendable ya que aun usando CoffeeScript y siendo ordenado el código se complejiza, muchas veces, mas de lo que esperamos o deseamos.

La experiencia del usuario con Ajax es bastante buena, porque la página nunca se pega y aparecen secciones con loaders mientras se completa el request, sin embargo, si el tiempo de procesamiento de una página completa no es muy larga, se recomienda traer toda la información necesaria para la pagina en el controlador.

#### Cuando si usar Ajax

Si se recomienda ocupar Ajax para los siguientes casos:

 - Cuando hay un modulo o una parte de la página que suele fallar o que
   depende de un tercero y no es fácil el manejo de errores de este
 - Cuando el procesamiento de la página web supera los 60 segundos, que
   es tiempo de timeout de los navegadores web, se puede dejar parte de
   la carga a llamadas Ajax para que alcance a cargar. Por ejemplo 11
   llamadas Ajax de de 6 segundos se pueden demorar, 7 a 10 segundos,
   mientras que haciendo todo ese procesamiento en el controlador se
   demorara 66 segundos y arrojara timeout.

Estas situaciones pueden suceder en dashboards en los cuales se calculan todas las estadísticas en tiempo real, lo cual no siempre es buena opción, ese tipo de decisiones son muy importantes al momento de crear un dashboard de estadísticas.

#### Nivel de complejidad del proyecto

Como se dijo anteriormente, al utilizar mucho Ajax en el proyecto, sobretodo si son llamadas anidadas, se complejiza bastante el código, por lo cual debe usarse en los casos que mencionamos antes y en los que se estime conveniente pero siempre teniendo el cuenta todo lo que hemos tratado en este capitulo.
