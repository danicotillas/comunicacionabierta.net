---
ID: 2062
post_title: >
  Cómo incluir una fuente / tipografía
  en tu web
author: danicotillas
post_excerpt: ""
layout: post
permalink: >
  https://comunicacionabierta.net/2017/06/incluir-fuente-tipografia-web/
published: true
post_date: 2017-06-07 11:11:32
---
Una de las cosas que normalmente queremos hacer en nuestra web y se nos complica es cambiar las fuentes (o fonts, o tipografías) que se muestran en pantalla. Son ya varios años que esto cambió para hacerse algo bastante fácil y accesible a cualquier mortal, sin necesidad de mucho conocimiento de código.

Para muchas personas lo más fácil es usar Google Fonts, pero no es muy recomendable. ¿Por qué? Por dos razones principales para mi. Una es que hace que se ralentice la carga de tu página ya que necesita ir a buscar las fuentes a otro servidor y así poder mostrarlas; la otra es que además Google usará el hecho de que estás mostrando las fuentes que te ofrece para recabar (uuuuuna vez más) datos sobre la navegación que tus visitantes hacen en la web. Es decir, vale que nos estén sacando datos cada dos por tres pero no es como para ponérselo aún más en bandeja por darnos un servicio de esos que llaman gratuitos donde el producto eres tú.

La opción que presento aquí permite mostrar las fonts libres que quieras en tu web sin mucho problema de uso de recursos de tu servidor además que toda la info queda en casa. Además sin la necesidad de un plugin extra, porque igual acaba siendo una lata tener que cuidar de la actualización de cada uno de ellos, temas de seguridad, etc...

<img class="aligncenter size-full wp-image-2283" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/06/typo.jpg" alt="" width="1024" height="768" />
<h2>Nuestra amiga la ardilla de las fuentes: FontSquirrel</h2>
La página web <a href="https://www.fontsquirrel.com">www.fontsquirrel.com</a> es una maravilla por muchas razones: vamos a encontrar fuentes 100% libres de uso comercial, vamos a poder descargarlas, instalarlas, utilizarlas, ... pero además viene que con algunas opciones que la hacen única.

<img class="size-full wp-image-2284 alignleft" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/06/fontsquirrel.jpg" alt="" width="293" height="186" />Por ejemplo el <a href="https://www.fontsquirrel.com/matcherator">Font Identifier</a> soluciona el dolor de cabeza que tenemos cuando se nos plantea la pregunta... ¿<strong>what the f***ont</strong> es la que aparece en esta imagen? Sólo arrastrando una imagen con la fuente en particular nos dará una serie de aproximaciones muy buenas.

Lo que nos interesa aquí es la parte de <strong><a href="https://www.fontsquirrel.com/tools/webfont-generator">WebFont Generator</a>: una herramienta para convertir nuestras fuentes a código web para utilizar directamente.</strong>

Para saber cómo funciona voy a hacer un pequeño fork del manual de <a href="https://www.arturogarcia.com/como-utilizar-cualquier-tipografia-en-wordpress/ la parte de font-squirrel">Arturo García</a> pensado para Wordpress pero que igual puede ser aplicado de forma manual en cualquier web:

<img class="aligncenter size-full wp-image-2281" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/06/webfont-generator.png" alt="" width="752" height="442" />

&nbsp;
<ul>
 	<li>Para añadir nuestra fuente, que también podemos haber descargado previamente de la misma web, pinchamos en <strong>"Upload Fonts", </strong>la subimos y marcamos la casilla de aceptación en la que declaras que tienes los permisos necesarios para utilizarla y pulsar en “Download your kit”. Te descargarás un archivo .zip. (Tip: ¿quieres encontrar buenas fuentes que van bien juntan? <a href="https://comunicacionabierta.net/tipografias-que-van-muy-bien-juntas/">Nodo Común te lo pone fácil en esta entrada</a>).</li>
</ul>
&nbsp;
<ul>
 	<li>Al abrir la carpeta de los archivos verás algo similar a esto:<code><strong><a href="https://www.comunicacionabierta.net/wp-content/uploads/2017/06/download-font.jpg"><img class="size-full wp-image-2282 alignright" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/06/download-font.jpg" alt="" width="411" height="170" /></a></strong></code>
Para utilizar la fuente necesitarás los archivos de fuente más el .css. Además si pinchas en el <strong>demo.html</strong> creado podrás ver cómo instalarla con instrucciones en inglés y un ejemplo de toda la fuente.<code><code></code></code><strong>Los 4 archivos de la fuente tendrás que subirlos a tu servidor, el css contiene el código que tendrás que añadir a tu web</strong> para que todo funcione correctamente.</li>
</ul>
&nbsp;
<ul>
 	<li>Ya estás listo para subir los archivos a tu servidor. Para hacerlo necesitas acceder al panel de control de tu hosting o tener alguna herramienta para acceder por ftp.Te recomiendo que crees<strong> una carpeta en la raíz de tu sitio y que la llames “fuentes”</strong>. Ahí subirás los archivos de extensión de tipografía.</li>
</ul>
&nbsp;
<ul>
 	<li>Ahora necesitas decirle a tu web qué tipografías tiene que mostrar y dónde puede encontrarlas. Eso lo haces con el código que encontrarás en el archivo css que descargaste junto con las fuentes.Si abres el css verás este texto:@font-face {
font-family: 'kollektifregular';
src: url('kollektif-webfont.woff2') format('woff2'),
url('kollektif-webfont.woff') format('woff');
font-weight: normal;
font-style: normal;}</li>
</ul>
Ese código presupone que vas a ubicar las tipografías en el directorio raíz de tu web pero<strong> te recomiendo que las coloques en la carpeta “fuentes”</strong>, tal como se explica anteriormente. Te ayudará a mantener todo más ordenado.

Por tanto tienes que hacer una pequeña modificación en el código. De forma que quede así:
<p style="padding-left: 30px;">@font-face {
font-family: 'kollektifregular';
src: url('<strong>https://tuweb.co/fuentes/</strong>kollektif-webfont.woff2') format('woff2'),
url('<strong>https://tuweb.co/fuentes/</strong>kollektif-webfont.woff') format('woff');
font-weight: normal;
font-style: normal;
}</p>
Lo que hemos hecho ha sido añadir la ruta dónde se encuentra la tipografía para que tu web la busque en el sitio adecuado, y con eso ya tienes el código listo para insertarlo en tu web.
<h3>¿Y ahora cómo hago para que se vea mi texto con esa fuente?</h3>
Tienes 3 opciones (desde Wordpress):
<ul>
 	<li>Si tu tema tiene algún lugar donde añadir tu propio CSS, pégalo ahí. La mayoría de temas cuentan ahora con esta opción de live CSS.</li>
 	<li>Si tu tema no te da esa opción, deberías crear un child theme para no modificar los archivos originales del tema.</li>
 	<li>Si no puedes añadir tu propio css al tema y no sabes cómo crear un child theme, no te queda otra que añadir el código al archivo css de tu tema. Esta opción tiene varios problemas, cuando se actualice el tema puedes perder los cambios y además, puede que la fuente no se muestre correctamente ya que estarás sobre escribiendo otros ajustes que venían por defecto. Antes de hacer cambios sobre este archivo te recomiendo que <strong>guardes una copia del css original</strong>, por si acaso.</li>
</ul>
Para editar el css del tema puedes hacerlo desde tu panel de control si es que usas Wordpress. Tienes que ir a “Apariencia &gt; Editor” y bajar hasta encontrar el archivo style.css.

En ese archivo es donde tienes que pegar el código css que has modificado anteriormente.

<img class="aligncenter size-full wp-image-2287" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/06/cualquier-tipografia-wordpress11.jpg" alt="" width="680" height="257" />

&nbsp;

Ya solo te queda un paso. En tu archivo css ya había unas fuentes predefinidas para mostrarse en cada elemento de la web.

Tienes que modificar algunas líneas del archivo css para que tu web sepa dónde tiene que mostrar tu nueva tipografía.

Por ejemplo, supongamos que quieres aplicar la fuente a los encabezados y que tienes el siguiente código por defecto en tu web:
<p style="padding-left: 30px;"><em>/* Headings */</em>
<em>H1,h2,h3,h4,h5,h6 {font-family: ‘Arial’, sans-serif;}</em></p>
Pues tendrías que cambiarlo para que deje de mostrar Arial en los encabezados y empiece a mostrar tu fuente, por ejemplo, si hubieras elegido Kollektif el código sería así:
<p style="padding-left: 30px;"><em>/* Headings */</em>
<em>H1,h2,h3,h4,h5,h6 {font-family: ‘<strong>kollektifregular</strong>‘, sans-serif;}</em></p>
Guardas los cambios y listo.

Si has hecho todo bien tu web empezará a mostrar tu tipografía en los lugares que hayas definido en el css.

&nbsp;

Créditos: Imagen de <a href="https://www.flickr.com/photos/adactio/5817844675">Jeremy Keith</a>.