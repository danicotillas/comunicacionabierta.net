---
ID: 2136
post_title: >
  Migrar un sitio de WordPress Multisite a
  un sitio individual
author: danicotillas
post_excerpt: >
  Si andas queriendo sacar tus sitios de
  WordPress instalados en un Multisite o
  WPMU, aquí te explico cómo. No hay una
  forma automática de hacerlo, pero al
  menos lograrás el objetivo aprendiendo
  de paso un poco más sobre bases de
  datos y uso de servidor y WordPress.
  Este manual es de nivel medio.
layout: post
permalink: >
  https://comunicacionabierta.net/2017/03/migrar-sitio-wordpress-multisite-sitio-individual/
published: true
post_date: 2017-03-30 11:08:07
---
Tal vez hubo un día en el que creíste que tener una instalación de WordPress Multisitios, o WordPress MU (WPMU) era una gran idea. Tal vez lo sigue siendo, o tal vez, como me ha pasado a mi, te ves en la necesidad de sacar uno de los sitios que tienes hospedados ahí para tenerlo como instalación individual.

La mayoría de la documentación que se encuentra <a href="https://code.tutsplus.com/tutorials/moving-wordpress-moving-a-site-out-of-a-multisite-network--cms-22772">es en inglés</a>, algo normal cuando hablamos de foros y aprendizaje sobre estos temas. Aquí pretendo explicarte de la mejor forma cómo puedes proceder si deseas pasar un sitio a una instalación propia.

Nunca está de más recordar.... ¡Haz una copia de seguridad de todo antes de nada! :) Gracias.
<h2>Entonces... paso por paso:</h2>
<ol class="ul1">
 	<li class="li1">Identifica el ID del sitio que quieres bajar. Si vas a network &gt; Sitios, pinchando sobre el que te interesa en la URL te vendra el "id=número".

<hr />

</li>
 	<li class="li1">Baja la Base de Datos (BD) a través de PHPMyAdmin en tu hosting (si, doy por hecho que lo tienes y sabes usarlo) seleccionando las tablas "wp_(número de sitio)" que corresponden a tu sitio. Se recomienda tomar una captura de pantalla para luego ver cuáles son las que tengo que borrar y reemplazar.

<hr />

</li>
 	<li class="li1">Abrirlo en <a href="https://www.sublimetext.com/">Sublime Text</a> (o cualquier otro editor de texto aunque este es bastante recomendable) y quitar el número para que quede wp_.

<hr />

</li>
 	<li class="li1">Subir wordpress limpio y crear como extensión de mi base de datos que sea "wp_". Una vez hecho, acceder por FTP y aumentar los archivos correspondientes a las carpetas /plugins /theme /uploads del número de sitio al que corresponde nuestra web.

<hr />

</li>
 	<li class="li1">Al subir el WordPress limpio se creará la base de datos con todas las tablas. Borrar las que tenemos guardadas y subir nuestro archivo a esta base de datos. Simplemente se agregarán.

<hr />

</li>
 	<li class="li1">Revisar la BD para ver que ninguna tabla tiene puesto el antiguo dominio. Sobre todo wp_site y wp_options.

<hr />

</li>
 	<li class="li1">Instalar “<a href="https://wordpress.org/plugins/better-search-replace/">Better Search &amp; Replace</a>” y buscar cadenas antiguas de imágenes o vínculos a posts. Este plugin prácticamente no necesita mucha explicación, una vez se instala se ve claramente dónde colocar la antigua url y la nueva, o parte de una cadena, por ejemplo: reemplazar "/uploads/site/5/" por "/uploads/" y de esa forma nos va a reconocer los archivos en la carpeta que queremos.</li>
</ol>
&nbsp;
<h3>¡Y listo!</h3>
¿Lo has intentado? ¿Te ha servido el breve manual? Si tienes cualquier problema puedes dejar un mensaje en comentarios y vemos la forma de arreglarlo. Si tienes una forma mejor de hacerlo, no dudes en pasarme el enlace para seguir aprendiendo.

&nbsp;
<h2></h2>
<h2>Actualización 31 mayo 2017</h2>
Ignacio Cerro, de <a href="https://imanguxara.com">imanguxara.com</a>, comentaba más abajo lo bueno que era poder acceder a esta entrada ya que tenía el mismo problema. Durante este mes hemos estado en un contacto bastante fluido y, lo mejor de todo, fructífero para aprender y mejorar la forma de hacerlo.

Aquí copio la forma en que lo explica él esperando que para aquellas personas que tengan que pasar por este tedioso proceso les sea aún más útil:

WPMU es una excelente solución en muchos casos cuando existe la necesidad de gestionar y mantener varios sitios webs basados en WordPress. Sin embargo, llega un momento en el que pueden pesar más los inconvenientes que los beneficios. La gestión de los backups y restauraciones en caso de error, actualización selectiva de plugins en función del sitio, antigüedad y tema o la simple posibilidad de facilitar la salida de uno de los sitios dentro del wpmu a un nuevo hospedaje son algunos de los motivos que nos pueden empujar a dejar atrás la instalación del wpmu.

Aquí planteamos cuáles deben ser los pasos a seguir para llevar un sitio dentro de una instalación de wpmu a su propia e independiente instalación.


1.- Lo primero que hay que hacer es instalar un nuevo wordpress con el dominio que nos interesa en el hospedaje que vayamos a usar.

2.- Si nos resulta posible, en el proceso de instalación vamos a determinar el prefijo de la base de datos. Para facilitar todo elegiremos el mismo prefijo que tiene ese sitio web en la instalación de wpmu dentro de su base de datos. Por ejemplo, en una instalación de wpmu podemos averiguar el id del sitio a migrar. El prefijo de la base de datos es habitualmente del tipo “wp_id_”. Por tanto, si, por ejemplo, el id del sitio a migrar es el 32, al instalar el nuevo wordpress elegiremos el prefijo" wp_32_” para la base de datos que se crea. phpMyAdmin nos ayuda a ver cómo es esto realmente. Si en el proceso de la instalación del nuevo wordpress no podemos o no sabemos cómo determinar el prefijo, deberemos tenerlo en cuenta a posteriori pues necesitamos este dato para poder avanzar.

3.- El siguiente paso es acceder a la base de datos del wpmu con phpMyAdmin. Nos muestra todas las tablas. Seleccionamos todas las que tengan el prefijo “wp_id_", siendo id el identificador del sitio que queremos migrar. Seleccionamos todas las tablas a excepción de:  options, users y usersmeta (no vamos a exportar las que aparezcan de estas tres). En la parte inferior de la pantalla, en el menú que dice “Para los elementos que están marcados” elegimos la opción Exportar. Elegimos la opción rápida y el formato SQL y pulsamos en continuar. Se descarga la base de datos en formato SQL.

4.- Pues bien, ya tenemos la base de datos del sitio que queremos migrar con lo que realmente necesitamos.

5.- Ahora descargamos vía ftp todas las imágenes que pertenecen al sitio que quiero exportar. En el wpmu están en la dirección httpdocs/wp-content/blogs-dir/ . Allí dentro volvemos a acudir al id del sitio a exportar. Estudiando las url en las que se guardan las imágenes del wpmu y de la nueva instalación y usando ftp, subimos al nuevo sitio las imágenes del antiguo.

6.- Hacemos lo mismo que en el paso anterior pero para el tema y los plugins usados.

7.- Hay que activar el tema y los plugins que se usen en el sitio de destino, tal cual estaban en el de origen.

8.- Ahora, usando phpMyAdmin, editamos la base de datos de la nueva web. Elegimos todas las tablas menos options, users y usersmeta y las eliminamos.

9.- Toca importar el archivo SQL previamente descargado.

10.- El proceso está terminado pero faltan pequeños ajustes. El primero es acudir al backend del nuevo sitio y determinar cuál debe ser la página de inicio de la web.

10.- A continuación hay que elegir la posición del menú existente en el sitio correcto dentro de Apariencia, menú.

11.- Casi hemos terminado pero hay que copiar los ajustes del tema del sitio antiguo al nuevo. Muchos temas incluyen la posibilidad de exportar e importar estos ajustes. En ocasiones es copiar y pegar una cadena de texto en el sitio correspondiente. Es algo que hay que buscar entre las opciones del tema.

12.- Por último, si hemos usado google maps, es probable que necesitemos reintroducir la API que nos permita la visualización de esos mapas.

Con esto, el resultado debe ser al 100% idéntico al de origen.