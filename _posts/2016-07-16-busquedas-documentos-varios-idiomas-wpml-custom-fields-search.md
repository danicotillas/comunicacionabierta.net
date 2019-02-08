---
ID: 1144
post_title: >
  Búsquedas de documentos en varios
  idiomas con WPML y Custom Fields Search
  en WordPress
author: danicotillas
post_excerpt: >
  Cómo lograr hacer búsquedas de
  documentos con campos personalizados en
  un Wordpress multilenguaje usando WPML y
  algunos plugins muy útiles.
layout: post
permalink: >
  https://comunicacionabierta.net/2016/07/busquedas-documentos-varios-idiomas-wpml-custom-fields-search/
published: true
post_date: 2016-07-16 18:54:20
---
Si estás trabajando en una web multi-idiomas y quieres subir documentos que tengan campos personalizados, una cosa que vas a querer es un buscador potente que te sirva para hacer las búsquedas en base a esos campos personalizados.

Voy a explicar aquí la forma que yo encontré en base a varios plugins bastante comunes pero que, de inicio, no ofrecen esa opción:
<ul>
 	<li><a href="https://wpml.org/"><strong>WPML (Wordpress Multilingual Plugin)</strong></a>: es el mejor plugin, sin duda, para lograr que nuestra web esté en varios idiomas. Y sí, es de pago.</li>
 	<li><strong><a href="https://www.advancedcustomfields.com/">ACF (Advanced Custom Fields)</a>:</strong> nos va a permitir crear los campos personalizados para nuestras entradas. Lo mejor que encontré en el plugin es que indicas bajo qué categoría querrás los campos personalizados, y al seleccionar esa categoría te aparecerán los campos automáticamente.</li>
 	<li><a href="https://wordpress.org/plugins/wp-custom-fields-search/"><strong>CFS (Custom Fields Search)</strong></a>: con este plugin podrás crear formularios de búsqueda a través de los campos personalizados creados con ACF.</li>
 	<li><a href="https://wordpress.org/plugins/widget-logic/"><strong>Widget Logic</strong></a>: nos permitirá seleccionar en qué páginas queremos que aparezca nuestro widget, en este caso nuestro buscador creado con CFS por idioma.</li>
</ul>
El problema encontrado es que CFS crea una búsqueda pero sólo en la base de datos del idioma principal que configuraste en WPML. De esta forma, aunque hayas traducido los campos de búsqueda de ACF y CFS, igualmente, al hacer una búsqueda en otro idioma directamente te buscará sólo en la del primer idioma. Además la extensión "WPML Widget" sólo funciona con los predeterminados, por lo que si queremos hacer un buscador en dos idiomas, tendremos que usar Widget Logic para explicarle al sistema cuándo tiene que mostrarlo.
<h2>Es decir</h2>
He trabajado en una web que usa dos idiomas: español e inglés. El idioma principal es el español.
<ul>
 	<li>Cree los campos personalizados de: autor, publicado por, año y palabra clave.</li>
 	<li>Traduje estos campos con WPML al inglés para que pudiesen aparecer en ese idioma.</li>
 	<li>Con CFS cree los widgets (uno para cada idioma) que me permite buscar en los campos personalizados previamente creado.</li>
 	<li>Con Widget Logic le explico al widget que sólo aparezca cuando la web esté en el idioma correcto con el código: <strong>ICL_LANGUAGE_CODE == 'es' </strong>para español, y <strong>ICL_LANGUAGE_CODE == 'en' </strong>para inglés.</li>
</ul>
<h2>Búsqueda diferenciada por idiomas</h2>
Aquí está la parte que más dolor de cabeza te va a dar si te pones a buscar en foros. Al parecer no es una opción que esté disponible, o pensada de antemano.

Al hacer la búsqueda en el formulario en inglés, seguía yendo a buscar a <strong>"https://url.com/?Search..."</strong> cuando lo que necesitaba era <strong>"https://url.com<span style="color: #ff0000;">/en/</span>?Search...".</strong>

Para ello, hay que ir a editar el plugin en las opciones de administración, y buscar el archivo:
<strong>wp-custom-fields-search/templates/wp-custom-fields-search-form.php</strong>

Una vez en él hay que reemplazar la línea:
<ul>
 	<li>&lt;form method='get' class='&lt;?php echo $formCssClass?&gt;' action='&lt;?php echo $formAction?&gt;'&gt;</li>
</ul>
Por:
<ul>
 	<li>&lt;?php
if (ICL_LANGUAGE_CODE == 'en'){ ?&gt;
&lt;form method='get' class='&lt;?php echo $formCssClass?&gt;' action='&lt;?php echo $formAction?&gt;/en/'&gt;
&lt;?php } else ?&gt;
&lt;form method='get' class='&lt;?php echo $formCssClass?&gt;' action='&lt;?php echo $formAction?&gt;'&gt;</li>
</ul>
Lo que le estaremos diciendo así al buscador es que cuando reconozca que el idioma es inglés entonces que le añada a la búsqueda <strong>/en/</strong> al final.

<hr />

Si, has llegado a esta entrada y aún no logras saber cómo poder hacerlo porque no quedó claro, escribe un comentario aquí abajo para poder intentar colaborarte. Yo no soy programador, de hecho tengo algunos conocimientos muy básicos, pero sí muy curioso como para lograr que finalmente las cosas funcionen como queremos.

Si, por otro lado, has llegado hasta este post y crees que existe una forma mejor de solucionar el problema, por favor, déjalo en comentarios para así poder aprender juntos.