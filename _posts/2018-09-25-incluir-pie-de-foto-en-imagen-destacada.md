---
ID: 2547
post_title: Incluir pie de foto en imagen destacada
author: danicotillas
post_excerpt: >
  Incluir el pie de foto en nuestras
  imágenes es algo necesario si queremos
  visibilizar de quien estamos
  aprovechando su trabajo, más aún
  cuando lo publica con licencia libre.
  Las imágenes destacadas no siempre
  vienen con esta opción. Aprende aquí
  cómo poder hacerlo.
layout: post
permalink: >
  https://comunicacionabierta.net/2018/09/incluir-pie-de-foto-en-imagen-destacada/
published: true
post_date: 2018-09-25 05:35:42
---
Una de las bases más importantes para sostener y validar la <a href="https://comunicacionabierta.net/blog/tag/cultura-libre/">Cultura Libre</a> es el hecho de respetar la mención de autoría, y mejor aún si la hacemos visible como se debe.

Páginas como <a href="https://unsplash.com/">Unsplash</a> están cambiando los formatos tradicionales (y en muchos casos horribles) de gestión privativa de imágenes, o de colocado de marca de agua. Si bien no es un sistema perfecto, es estupendo para poder contar con imágenes de alta calidad para nuestros proyectos y trabajos, y al fin y al cabo sólo se nos pide que <strong>amablemente</strong> citemos la fuente ya que son todas de Dominio Público, por lo que no tenemos obligación.

Pero como somos simpáticos hasta decir basta, queremos poder colocar la autoría incluso en las imágenes destacadas de nuestras entradas en Wordpress. Algo que no siempre es fácil según el tema. Es ese campo de "Leyenda" que vemos al subir una imagen y que a veces ni siquiera rellenamos.

A continuación una explicación de cómo poder hacerlo encontrada junto a <a href="https://mundoenmovimiento.org/impulsa/maria-penalosa-mendez/">María Peñalosa Méndez</a> y <a href="https://mundoenmovimiento.org/impulsa/miguel-m-serrano/">Miguel M. Serrano</a> mientras veíamos cómo solucionarlo para el proyecto de <a href="https://mundoenmovimiento.org">Mundo en Movimiento</a>. Puedes ver aquí de dónde sacamos la info: <a href="https://napitwptech.com/tutorial/wordpress-development/display-image-caption-added-wordpress/">https://napitwptech.com/tutorial/wordpress-development/display-image-caption-added-wordpress/</a>
<h2>Incluir el pie de foto en nuestro tema</h2>
&nbsp;
<p class="p1"><b>Vamos a single.php e incluimos el siguiente texto (en el tema que estoy utilizando es ahí dónde se muestran los post individuales, tendrías que buscar "ese" archivo en tu tema)</b></p>
<p class="p1" style="padding-left: 30px;">&lt;!--INCLUSIÓN PIE DE FOTO EN FEATURED IMAGE --&gt;
&lt;?php if (get_post(get_post_thumbnail_id())-&gt;post_excerpt) { // search for if the image has caption added on it ?&gt;
<span class="Apple-converted-space">    </span>&lt;div class="featured-image-caption"&gt;
<span class="Apple-converted-space">        </span>&lt;?php echo wp_kses_post(get_post(get_post_thumbnail_id())-&gt;post_excerpt); // displays the image caption ?&gt;
<span class="Apple-converted-space">    </span>&lt;/div&gt;
&lt;?php } ?&gt;</p>
<p class="p1"><b>Luego en el campo de CSS personalizado podemos poner algo como</b></p>
<p class="p1" style="padding-left: 30px;">.featured-image-caption {
position: relative;
font-size: 11px;
text-align: right;
padding-right: 20px;
margin-top: -40px;
}</p>
Obviamente el CSS es algo personal para cada web. A mi me vino bien este para que se mostrase <a href="https://mundoenmovimiento.org/articulo/concentraciones-en-19-ciudades-espanolas-para-gritar-stopdevolucionesexpress/">así de chulo</a>. Pero para gustos, colores, así que maquéate el tuyo y me lo cuentas en los comentarios.