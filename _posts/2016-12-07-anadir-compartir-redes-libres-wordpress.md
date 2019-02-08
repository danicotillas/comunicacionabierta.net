---
ID: 1871
post_title: 'Cómo añadir &#8220;compartir en redes libres&#8221; en WordPress'
author: danicotillas
post_excerpt: ""
layout: post
permalink: >
  https://comunicacionabierta.net/2016/12/anadir-compartir-redes-libres-wordpress/
published: true
post_date: 2016-12-07 18:52:32
---
En este pequeño manual te mostraremos cómo dar a tus lectores la posibilidad de compartir en redes libres. En particular veremos cómo compartir en <a href="https://es.wikipedia.org/wiki/GNU_Social" target="_blank" rel="noopener" data-cke-saved-href="https://es.wikipedia.org/wiki/GNU_Social"><strong>GNUSocial</strong></a> y <a href="https://es.wikipedia.org/wiki/Diaspora_(red_social)" target="_blank" rel="noopener" data-cke-saved-href="https://es.wikipedia.org/wiki/Diaspora_(red_social)"><strong>Diaspora</strong></a>.

En los gestores de contenido, existen muchas formas de agregar "compartir en..." (usando módulos o plugins) pero hay pocos que tengan la posibilidad de hacerlo en las redes sociales libres.

<a href="https://jetpack.com/"><img class="alignright wp-image-1885 size-full" src="https://www.comunicacionabierta.net/wp-content/uploads/2016/12/jetpack-1.png" width="238" height="153" /></a>Hay un plugin muy utilizado, que tiene muchas funcionalidades y se llama <a href="https://jetpack.com/"><strong>Jetpack</strong></a>. Para instalarlo y configurarlo debes tener una cuenta en <a href="https://wordpress.com/">WordPress.com</a>. Esto no quiere decir que tu sitio deba estar alojado allí. Recuerda que WordPress puede ser instalado en cualquier servidor, pero la cuenta sí la necesitarás para configurar <strong>Jetpack.</strong>
<h3>Vamos paso por paso desde aquí...</h3>
<a href="https://www.comunicacionabierta.net/wp-content/uploads/2016/12/compartir.png"><img class="size-medium wp-image-1875 alignright" src="https://www.comunicacionabierta.net/wp-content/uploads/2016/12/compartir-300x172.png" alt="" width="300" height="172" /></a><strong>1.-</strong> Una vez que lo hayas<strong> instalado y configurado,</strong> debes habilitar la<strong> funcionalidad "Compartir"</strong> (dentro de Jetpack &gt; Configuración).

&nbsp;

&nbsp;

<hr />

<a href="https://www.comunicacionabierta.net/wp-content/uploads/2016/12/ajustes-compartir.png"><img class="size-medium wp-image-1874 alignright" src="https://www.comunicacionabierta.net/wp-content/uploads/2016/12/ajustes-compartir-300x72.png" alt="" width="300" height="72" /></a><strong>2.-</strong> Luego accedes a los <strong><em>Ajustes</em> </strong>de tu sitio y aparece un nuevo elemento llamado "Compartir". Verás allí la sección de<strong> "Servicios disponibles",</strong> donde están las clásicas y centralizadas redes sociales.

<hr />

<a href="https://www.comunicacionabierta.net/wp-content/uploads/2016/12/botones-compartir.png"><img class="size-medium wp-image-1876 alignright" src="https://www.comunicacionabierta.net/wp-content/uploads/2016/12/botones-compartir-300x165.png" alt="" width="300" height="165" /></a><strong>3.-</strong> Aquí viene la parte divertida, ya que puedes agregar tus propios servicios: <em>Añadir un servicio nuevo. </em>Al hacer clic allí, aparecerán 3 campos a completar y aquí te dejamos 2 propuestas:

<em><em>Recuerda que debes remplazar <strong>https://www.tusitio.com</strong> con lo que corresponda; además asumimos que tu WordPress está configurado para mostrar el nombre del artículo en la URL, lo cual haces desde <strong>https://www.tusitio.com/wp-admin/options-permalink.php</strong></em></em>

<hr />

<h4><strong>GNUSocial:</strong></h4>
<strong>Nombre:</strong> GNUSocial
<strong>Compartiendo URL:</strong> https://gs-share.tedic.org/gs-share-es.php?url=%post_full_url%&amp;title=%post_title%<code>
</code><strong>URL del icono:</strong> https://gs-share.tedic.org/images/gs-share.png

<hr />

<h4><strong>Diaspora:</strong></h4>
<strong>Nombre:</strong> Diaspora
<strong>Compartiendo URL:</strong> https://sharetodiaspora.github.io/?title=%post_title%&amp;url=%post_full_url%<code>
</code><strong>URL del icono:</strong> https://www.tedic.org/wp-content/uploads/sites/4/2016/06/diaspora.png

<hr />

&nbsp;
<h3>ACTUALIZACIÓN 27 de septiembre de 2018</h3>
Hace unos días que vi que ya no funcionaba la opción de compartir por GNUSocial, lo cual hacía que este manual se quedase obsoleto.

El genial victorhck explica en este post - <a href="https://victorhckinthefreeworld.com/2018/04/06/como-anadir-un-boton-en-tu-wordpress-para-compartir-contenido-en-mastodon-diaspora-gnusocial-o-hubzilla/">https://victorhckinthefreeworld.com/2018/04/06/como-anadir-un-boton-en-tu-wordpress-para-compartir-contenido-en-mastodon-diaspora-gnusocial-o-hubzilla/</a> - como poder agregar el botón gracias al desarrollo de código del también genial <a href="https://mastodont.cat/@surtdelcercle">Kim</a> (como ya he hecho yo en Comunicación Abierta) para compartir en redes libres a través de un interesante sistema.

Adelante, no dejes de leerle e implementarlo... y de compartir en redes libres!

&nbsp;
<h4>¡Esperamos que te haya sido de utilidad!</h4>
&nbsp;

Este manual ha sido creado en colaboración entre <a href="https://www.tedic.org/">TEDIC</a> y <a href="https://comunicacionabierta.net">Comunicación Abierta</a>.

<em>Imagen de portada "<a href="https://es.wikipedia.org/wiki/Teselado_triangular#/media/File:Tiling_Regular_3-6_Triangular.svg">Teselado Triangular</a>" de <a title="User:Nonenmac" href="https://commons.wikimedia.org/wiki/User:Nonenmac">R. A. Nonenmacher</a> bajo licencia CC BY SA</em>