---
ID: 2789
post_title: >
  Cómo añadir categorías personalizadas
  para elegir en entradas usando Gutenberg
  con WordPress
author: danicotillas
post_excerpt: ""
layout: post
permalink: >
  https://comunicacionabierta.net/2019/05/como-anadir-categorias-personalizadas-para-elegir-en-entradas-usando-gutenberg-con-wordpress/
published: true
post_date: 2019-05-19 09:18:18
---
<!-- wp:paragraph -->
<p>Últimamente estoy usando mucho Themify y las posibilidades que ofrece de Custom Post Types (Tipos de entrada personalizadas). Además, viene con la opción de crear nuevas taxonomías, entonces no sólo tienes que elegir entre Categorías y Etiquetas, sino que puedes crear nuevas familias, como por ejemplo: Tipo de proceso, Tipo de proyecto o Saber hacer de (algo que me gusta mucho aplicar en webs que reflejan el trabajo como suma de esfuerzos colectivos.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Por defecto Gutenberg no lo reconoce así que tienes que sumar este código a tu functions.php cambiando el nombre de <strong>get_taxonomy</strong> que aparece ahí por tu propio código.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Te debería funcionar sin problema.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>function wc_product_category_add_tax_to_api() {
	$mytax = get_taxonomy( 'tipo_proceso' ); $mytax->show_in_rest = true; $mytax = get_taxonomy( 'tipo_proyecto' ); $mytax->show_in_rest = true; $mytax = get_taxonomy( 'saber_hacer' ); $mytax->show_in_rest = true; $mytax = get_taxonomy( 'tipo_implicacion' ); $mytax->show_in_rest = true; }
	add_action( 'init', 'wc_product_category_add_tax_to_api', 30 );</code></pre>
<!-- /wp:code -->