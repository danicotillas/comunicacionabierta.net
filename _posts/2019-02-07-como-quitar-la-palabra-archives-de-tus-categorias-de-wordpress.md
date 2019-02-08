---
ID: 2712
post_title: 'Cómo quitar la palabra &#8220;Archives&#8221; de tus categorías de WordPress'
author: danicotillas
post_excerpt: ""
layout: post
permalink: >
  https://comunicacionabierta.net/2019/02/como-quitar-la-palabra-archives-de-tus-categorias-de-wordpress/
published: true
post_date: 2019-02-07 08:28:06
---
La solución que he encontrado a esto, que en muchas ocasiones queda muy feo, viene explicada en <a href="https://www.quora.com/Wordpress-How-to-remove-word-Archive-from-Category-Tag-title">Quora.com</a>.

Hay que poner este código en tu archivo de functions.php. Deseablemente en tu tema child para que no se borre si tienes alguna actualización.
<pre>add_filter( 'get_the_archive_title', function ($title) {
if ( is_category() ) {
$title = single_cat_title( '', false );
} elseif ( is_tag() ) {
$title = single_tag_title( '', false );
} elseif ( is_author() ) {
$title = '<span class="vcard">' . get_the_author() . '</span>' ;
}

return $title;
});</pre>