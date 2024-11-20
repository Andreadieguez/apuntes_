# Tema 2 LMSGI Utilización de lenguajes de marcas en entornos web.

Los lenguajes de marca son los que usan `<etiquetas>`para estructurarse, así facilitan su interpretación. `[HTML o XML]`
 - HTML: HyperText Markup Language - Lenguaje de Marcas de Hipertexto, el componente más básico de la Web. Su evolcuión va desde el HTML al HTML 5.0. Flexible con la sintaxis.
 - XHTML: Extensive Hypertext Markup Language; Versión más estricta de `[HTML]` basada en `[XML]`. Sintaxis más rigurosa (etiquetas bien cerradas, minúsculas, etc.).


**Estructura de un documento HTML**

```html
<!DOCTYPE html> <!-- Define el tipo de documento como HTML5 -->
<html lang="es"> <!-- Indica que el contenido está en español -->
    <head> <!-- Contenedor de metadatos y recursos de la página -->
        <meta charset="UTF-8"> <!-- Establece la codificación de caracteres a UTF-8 -->
        <meta name="viewport" content="width=device-width, initial-scale=1.0"> <!-- Asegura que la página sea responsiva en dispositivos móviles -->
        <title>Título del Documento</title> <!-- Define el título de la página (visible en la pestaña del navegador) -->
    </head>
    <body> <!-- Contenedor del contenido visible de la página -->
        <h1>Bienvenido</h1> <!-- Título principal visible en la página -->
        <p>Este es un ejemplo de estructura básica de HTML.</p> <!-- Párrafo de texto que describe el contenido -->
    </body>
</html>
```

**Etiquetas y atributos**

En HTML, las *etiquetas* son elementos predefinidos que estructuran el contenido, mientras que los *atributos* son propiedades adicionales que proporcionan información extra a esas etiquetas. Están limitadas a un conjunto establecido y los atributos pueden ser comunes en varias etiquetas.

### **Etiquetas: Dicen al navegador qué tipo de contenido o estructura utilizar**
```html
<p> P sería una etiqueta, define lo que vemos como párrafo</p> <!-- <p> es la etiqueta para definir un párrafo -->
```
### **Atributos: Proporciona información, valor adicional a la etiqueta.**
```html
<img src="aquilarutadelaimagen.jpg" alt="Descripción de la imagen"> <!-- src (la fuente de la imagen) y alt (descripción de la imagen)ambos son atributos de la etiqueta <img> -->
```
Los atributos comunes en HTML suelen ser los que se usan en casi todas las etiquetas: 

```html
<!-- NAME: Atributo que asigna un nombre a un formulario, por ejemplo. -->
<form name="miFormulario">Formulario de ejemplo</form>

<!-- TITLE: Atributo que proporciona una descripción que aparece al pasar el ratón sobre el elemento -->
<img src="imagen.jpg" title="Imagen de ejemplo">

<!-- ID: Atributo que permite identificar un elemento de manera única en la página -->
<div id="contenidoPrincipal">Contenido principal</div>

<!-- STYLE: Atributo que aplica un estilo directo al elemento -->
<p style="color:blue;">Texto en azul</p>

<!-- CLASS: Atributo que asigna una clase a un elemento para aplicar estilos definidos en CSS -->
<p class="destacado">Texto destacado</p>
```
Los atributos de internacionalización como `<dir>`, `<lang>`, y `<xml:lang>`, se utilizan para definir el idioma o la dirección del texto.


### **Elemento: es el espacio que se ocupa en un documento.**
Existen dos tipos de elementos: en bloques (block) o en lineas (inline). 

**Elementos de bloque**: 
        - Comienzan en una nueva línea y ocupan todo el espacio disponible.
        - Ejemplos: **`<div>`, `<h1-h6>`, `<p>`, `<table>`, `<ol-ul-li>`, `<aside>`, `<header>`, `<footer>`, `<section>`, `<address>`, `<nav>`, `<html>`, `<head>`, `<body>`**...

**Elementos en línea**: 
        - Ocupan solo el espacio necesario.
        - No crean saltos de línea.
        - Ejemplos: **`<a>`, `<strong>`, `<span>`, `<img>`, `<em>`, `<b>`, `<i>`,`<object>`, `<label>`, `<tt>`**...

Un elemento HTML se compone de:

1. Etiqueta de apertura: Inicia el elemento. Ejemplo: `<p>`.
2. Atributos (opcionales): Información adicional dentro de la etiqueta.  
3. Texto (opcional): Contenido entre las etiquetas.
4. Etiqueta de cierre: Finaliza el elemento. Ejemplo: `</p>`.
Nota: Algunos elementos no tienen cierre, como `<img>` y se denominan **elementos auto-cerrables**..

**Elementos del HEAD (Block-level elements)**
    Son de dos tipos:
1. Elementos Contenedores:
    - **`<title>`**: Define el título del documento, que aparece en la barra del navegador y en la pestaña. Es **obligatorio**.
    - **`<script>`**: Permite incrustar scripts. Su contenido debe estar entre marcas de comentarios para evitar su interpretación como texto HTML.
    - **`<style>`**: Define estilos CSS aplicados al documento. También debe estar entre marcas de comentarios para evitar su interpretación como texto HTML.

2. Elementos No Contenedores:
    - **`<base>`**: Establece la URI base del documento para los enlaces relativos.
    - **`<isindex>`**: Permite un prompt de entrada de datos (ha sido eliminado de los estándares web, aunque algunos navegadores lo siguen soportando).
    - **`<link>`**: Define enlaces a documentos externos, como hojas de estilo CSS o fuentes.
    - **`<meta>`**: Proporciona metadatos sobre la página, como la codificación de caracteres, descripción, autores, etc.

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <meta charset="UTF-8">
            <title>El título es obligatorio</title>
        </head>
        <body>
            ...
        </body>
    </html>

10. **Encabezados y párrafos**
    El texto se delimita a través de varias etiquetas:
    `<p>` (párrafo), `<h1-h6>` (encabezados), `<tittle>` (titulo que define el HTML), `<blockquote>` (Citas o fragmentos de texto), `<pre>`(texto preformateado)

11. **Saltos de Línea y Espacios en Blanco** 
    Los navegadores ignoran saltos de línea y colapsan espacios consecutivos. Usa `<br>` para saltos de línea y `&nbsp;` para espacios múltiples.

12. **Comentarios**
    Los comentarios en HTML se escriben con `<!-- comentario -->` y no son procesados por los navegadores. Pueden ser multilinea.

13. **Semántica a Nivel de Texto**
    Elementos útiles: `<a>` para hipervínculos, `<strong>` para texto importante, `<em>` para énfasis, `<small>` para texto accesorio, `<br>` para saltos de línea.

14. **Listas**
    Existen tres tipos de listas: desordenadas (`<ul>`), ordenadas (`<ol>`) y de definición (`<dl>`), cada una con elementos específicos como `<li>`, `<dt>`, y `<dd>`.

15. **Tablas**
    Las tablas se definen con `<table>`, filas con `<tr>`, celdas con `<td>`, y cabeceras con `<th>`. También se puede usar `<caption>`, `<thead>`, `<tbody>`, y `<tfoot>`.

16. **Formularios**  
    Los formularios se definen con `<form>`. Atributos clave: `name` (nombre), `action` (acción a ejecutar), `method` (GET o POST) y `enctype` (formato de envío).  
    ```html
    <form name="miFormulario" action="/procesar.php" method="post">
    ```

17. **Campos de formulario - input**  
    El `<input>` se usa para diferentes controles como texto, contraseñas, botones de radio. Atributos importantes: `name`, `size`, `maxlength`, `value`, `placeholder`.  
    ```html
    <input type="text" name="usuario" required>
    ```

18. **Campos de formulario - Área de texto**  
    El `<textarea>` permite un texto más largo y se define con `rows` (filas) y `cols` (columnas).  
    ```html
    <textarea name="comentarios" rows="4" cols="50"></textarea>
    ```

19. **Campos de formulario - Lista desplegable**  
    El `<select>` permite que el usuario seleccione opciones de una lista. Se define con `<option>` para cada opción.  
    ```html
    <select name="sistema">
        <option value="Linux">Linux</option>
        <option value="Windows">Windows</option>
    </select>
    ```

20. **Campos de formulario - Checkbox**  
    El `<input type="checkbox">` permite seleccionar una o más opciones.  
    ```html
    <input type="checkbox" name="aceptar" checked>
    ```

21. **Botones de formulario**  
    - **Botón de envío**: `<input type="submit">` envía el formulario.  
    - **Botón de anulación**: `<input type="reset">` borra los campos del formulario.  
    ```html
    <input type="submit" value="Enviar">
    <input type="reset" value="Borrar">
    ```

22. **Otros campos de formulario**  
    Otros campos incluyen:  
    - **Oculto**: `<input type="hidden">`  
    - **Contraseña**: `<input type="password">`  
    - **Archivo**: `<input type="file">`  
    - **Email**: `<input type="email">` valida el formato.
    ```html
    <input type="email" name="email" required>
    ```

23. **Campos de formulario con formato de fecha**  
    Campos para seleccionar fechas, como: `<input type="date">`, `<input type="time">`, `<input type="datetime-local">`.  
    ```html
    <input type="date" name="fecha">
    ```

24. **Campos de formulario - Rangos**  
    El `<input type="range">` permite seleccionar un valor dentro de un rango.  
    ```html
    <input type="range" min="1" max="100" step="1">
    ```

25. **Organización de formularios**  
    Usa `<label>` para asociar etiquetas con campos y `<fieldset>` para agrupar los campos de un formulario.  
    ```html
    <fieldset>
        <legend>Datos Personales</legend>
        <input type="text" name="nombre">
    </fieldset>
    ```

26. **Multimedia**  
    Elementos como `<img>` (para imágenes), `<audio>` (para audio), `<video>` (para video) y `<object>` (para contenido multimedia general) se utilizan para insertar contenido multimedia.  
    ```html
    <img src="logo.jpg" alt="Logo" width="100" height="100">
    ```

27. **Elemento `<img>`**  
    Se usa para insertar imágenes. Atributos: `src` (ruta), `alt` (texto alternativo), `height` y `width`.  
    ```html
    <img src="logo.jpg" alt="Logo" width="100" height="100">
    ```

28. **Secciones y etiquetas semánticas**  
    HTML5 incluye etiquetas semánticas como `<header>`, `<footer>`, `<section>`, `<article>`, `<aside>`, `<nav>` para estructurar mejor el contenido.  
    ```html
    <header>
        <h1>Bienvenidos a mi sitio web</h1>
    </header>
    ```

29. **Elemento iframe**  
    El `<iframe>` permite insertar una página web dentro de otra. Atributos: `src` (contenido), `height` (alto), `width` (ancho).  
    ```html
    <iframe src="pagina.html" width="600" height="400"></iframe>
    ```

30. **Validación HTML**  
    Puedes validar tu código HTML con herramientas en línea como el validador W3C o Validator.nu para asegurarte de que cumpla con las normas de HTML5.  
    ```html
    <!-- Validación del código HTML -->
    <form action="https://validator.w3.org/nu/" method="get">
    </form>
    ```

31. **Hojas de estilo / CSS**  
    CSS (Cascading Style Sheets) permite a los desarrolladores web controlar el estilo y el formato de múltiples páginas al mismo tiempo.  

33. **Ilustración de una cascada**  
    Las hojas de estilo CSS permiten aplicar estilos a múltiples páginas web de un sitio, separando el contenido y el formato. Esto reduce la dificultad de 0,,0actualizar el diseño en todo el sitio.  
    CSS se compone de reglas que afectan a los documentos HTML o XML.  
    - **CSS 1**: Publicado en 1996 como la primera recomendación oficial.  
    - **CSS 2**: Publicado en 1998, con más mejoras.  
    - **CSS 3**: Empezó a desarrollarse en 1998 y se divide en módulos para una evolución más flexible.  
    - **CSS 4**: No tiene una especificación integrada, ya que está basado en módulos que se actualizan independientemente.  

34. **Autoevaluación**  
    Las hojas de estilo en cascada permiten:  
    - Definir formatos que se aplican a varias páginas web de un sitio.  
    - Separar el formato de la estructura de la página web.  

35. **Cómo incluir CSS en un documento HTML o XHTML**  
    Existen tres formas de aplicar CSS a una página HTML:  
    1. **Declaración en línea**: Se declara el estilo en la misma etiqueta HTML. Aunque es funcional, se desaconseja para mantener la separación de contenido y formato.  
    ```html
    <p style="color: red;">Texto en rojo</p>
    ```  
    2. **Declaración interna**: Se incluyen los estilos en el encabezado del documento, dentro de las etiquetas `<style>`.  
    ```html
    <html>
        <head>
            <style type="text/css">
                p {color: green;}
            </style>
        </head>
        <body>
            <p>Hola</p>
        </body>
    </html>
    ```  
    3. **Declaración externa**: Se vincula un archivo CSS externo en el encabezado con la etiqueta `<link>`.  
    ```html
    <html>
        <head>
            <link rel="stylesheet" type="text/css" href="estilos.css">
        </head>
        <body>
            <p>Hola</p>
        </body>
    </html>
    ```  
    El archivo `estilos.css` tendrá el siguiente contenido:
    ```css
    p {color: green;}
    ```

36. **Autoevaluación**  
    El mejor modo de aplicar formatos a una página web es:  
    - Definiendo un archivo CSS externo.

37. **Elemento `<span>`**  
    El `<span>` se usa para aplicar estilo a texto dentro de un bloque sin modificar la estructura.  
    Ejemplo:
    ```html
    <p>Parte de este párrafo <span style="color:red">está en rojo</span></p>
    ```

38. **Sintaxis de las reglas de estilo**  
    Las reglas CSS están formadas por un **selector**, que indica el elemento a estilizar, y una **declaración**, que especifica el estilo a aplicar. La declaración contiene:
    - **Propiedad**: el atributo que se quiere modificar.
    - **Valor**: el nuevo valor de la propiedad.  
    Ejemplo:
    ```css
    p { color: blue; }
    ```
    Aquí, el selector es `p`, la propiedad es `color`, y el valor es `blue`.

39. **Autoevaluación**  
    El elemento HTML sobre el que se aplica un estilo se especifica:  
    - En etiquetas, es decir, entre `<` y `>`.  

40. **Cascada y herencia de estilos**  
    Cuando hay estilos contradictorios, el navegador aplica la siguiente precedencia:  
    1. Declaración en línea.  
    2. Declaración interna.  
    3. Declaración externa.  
    4. Propiedades por defecto del navegador.  
    Además, los estilos se pueden heredar. Por ejemplo, si un elemento está dentro de otro, puede heredar los estilos del elemento externo, siempre y cuando no tengan estilos definidos.

41. **Selectores**  
    Los **selectores** permiten especificar a qué elementos HTML aplicar los estilos. Algunos de los más comunes son:  
    - **Selector universal (`*`)**: Selecciona todos los elementos.  
    ```css
    * { margin: 10px; padding: 5px; }
    ```  
    - **Selectores de etiqueta**: Aplica el estilo a todas las etiquetas del tipo especificado.  
    ```css
    p { text-align: center; }
    ```  
    - **Selectores combinados**: Se aplican a varios tipos de elementos.  
    ```css
    p, h1, h2 { text-align: center; }
    ```

42. **Selectores de clase**  
    El **selector de clase** permite aplicar un estilo a todos los elementos que tengan una clase específica.  
    Ejemplo:
    ```html
    <p class="parrafoCentrado">Texto centrado</p>
    ```
    Y el CSS sería:
    ```css
    .parrafoCentrado { text-align: center; }
    ```

43. **Selectores de ID**  
    El **selector de ID** se usa para aplicar estilos a un único elemento, ya que el ID debe ser único en cada página.  
    Ejemplo:
    ```html
    <p id="unico">Texto único</p>
    ```
    Y el CSS sería:
    ```css
    #unico { color: blue; }
    ```
