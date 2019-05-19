---
ID: 2779
post_title: >
  Mostrar imagen destacada (Featured
  image) antes del contenido de una
  entrada (post)
author: danicotillas
post_excerpt: ""
layout: post
permalink: >
  https://comunicacionabierta.net/2019/05/mostrar-imagen-destacada-featured-image-antes-del-contenido-de-una-entrada-post/
published: true
post_date: 2019-05-19 05:26:05
---
<!-- wp:paragraph -->
<p>En algunos temas de WordPress no se hace posible ver la imagen destacada en el cuerpo de la entrada, como por ejemplo en este mismo blog. Hace un tiempo cambié esa opción y cree la posibilidad gracias al siguiente post:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://wpsites.net/web-design/add-featured-image-before-content-in-any-theme/">Add Featured Image Before Content In Any Theme</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>En mi caso sólo hizo falta sumarle este pedazo de código al functions.php dentro del child theme para no generar problemas en caso de actualización.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Y de paso le metí unos saltos de línea &lt;br> para que así no aparezca el texto pegado a la imagen.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>add_filter( 'the_content', 'wpsites_featured_image_before_content' ); 

function wpsites_featured_image_before_content( $content ) { 
if ( is_singular('post') &amp;&amp; has_post_thumbnail()) {
        $featuredimage = get_the_post_thumbnail();
		
        $content = $featuredimage . '&lt;br>&lt;br>' . $content;
		
		}

    return $content;
}</code></pre>
<!-- /wp:code -->