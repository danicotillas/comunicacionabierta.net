---
ID: 2579
post_title: >
  Cómo hacer que sólo el admin de un
  WordPress pueda entrar al administrador
author: danicotillas
post_excerpt: |
  - ¡Knock knock!
  - ¿Quién es?
  - Un colaborador.
  - Lo sentimos, mejor quédese en el patio de entradas.
layout: post
permalink: >
  https://comunicacionabierta.net/2018/10/como-hacer-que-solo-el-admin-de-un-wordpress-pueda-entrar-al-administrador/
published: true
post_date: 2018-10-30 11:14:17
---
Trabajando con Buddypress una cosa MUY importante es que puedas controlar quién entra al wp-admin. Lo que en un principio puede parecer fácil, luego se te complica de inicio, para al final darte cuenta que existía un plugin... como para casi todo: alguien pasó por ese problema antes que tú y lo solucionó.
¡Larga vida al software libre y el conocimiento abierto!

Aquí las soluciones que yo encontré para mis problemas específicos.
<h3>Con código</h3>
Coloca en functions.php
<pre style="padding-left: 30px;">function redirect_user_homepage() {
if ( is_user_logged_in() &amp;&amp; is_admin() &amp;&amp; !current_user_can( 'administrator' ) ) {
wp_redirect( home_url() );
exit;
}
}
add_action( 'init', 'redirect_user_homepage' );</pre>
<h3></h3>
<h3>Con plugin</h3>
Otra opción con plugin sería instalar <a href="https://es.wordpress.org/plugins/remove-dashboard-access-for-non-admins/">Remove Dashboard Access</a>.

Yo tenía colocado el código anterior pero en instalaciones como <a href="https://investigacionsocial.net">Investigación Social punto Net</a> donde además se cuenta con <a href="https://wordpress.org/plugins/social-articles/">Social Articles</a> no me preguntéis por qué pero ese código de arriba hace que no se puedan subir imágenes destacadas a las notas. Por ello he optado finalmente por instalar el plugin ya que hace que el resto de cosas funcione.