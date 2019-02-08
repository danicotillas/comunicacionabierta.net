---
ID: 2581
post_title: >
  Soluciona el envío de email de
  activación en Buddypress
author: danicotillas
post_excerpt: >
  Porque si te abres una cuenta en una red
  social es importante que certifiques que
  el email es tuyo, también lo es poder
  recibir ese email para validarla. Aquí
  un truco para que no te falle
  Buddypress.
layout: post
permalink: >
  https://comunicacionabierta.net/2018/10/soluciona-el-envio-de-email-de-activacion-en-buddypress/
published: true
post_date: 2018-10-30 11:21:36
---
Una cosa horrible que pasa cuando usas el querido <a href="https://es.buddypress.org/">Buddypress</a> es que el envío de email de activación no acaba de funcionar bien del todo. Navegando por los mares de bits encontré este truco que apunté en un post-it y ahora no recuerdo de quién era, pero mío no ¡eso seguro!

Con hacer lo que sigue a mi me ha funcionado bastante bien hasta ahora:

En<strong> buddypress/bp-core/bp-core-functions.php </strong>reemplazar:
<pre style="padding-left: 30px;">'core-user-registration' =&gt; array(
/* translators: do not remove {} brackets or translate its contents. */
'post_title' =&gt; __( '[{{{site.name}}}] Activate your account', 'buddypress' ),
/* translators: do not remove {} brackets or translate its contents. */
'post_content' =&gt; __( "Thanks for registering!\n\nTo complete the activation of your account, go to the following link and click on the &lt;strong&gt;Activate&lt;/strong&gt; button:\n&lt;a href=\"{{{activate.url}}}\"&gt;{{{activate.url}}}&lt;/a&gt;\n\nIf the 'Activation Key' field is empty, copy and paste the following into the field - {{key}}", 'buddypress' ),
/* translators: do not remove {} brackets or translate its contents. */
'post_excerpt' =&gt; __( "Thanks for registering!\n\nTo complete the activation of your account, go to the following link and click on the 'Activate' button: {{{activate.url}}}\n\nIf the 'Activation Key' field is empty, copy and paste the following into the field - {{key}}", 'buddypress' )
),
'core-user-registration-with-blog' =&gt; array(
/* translators: do not remove {} brackets or translate its contents. */
'post_title' =&gt; __( '[{{{site.name}}}] Activate {{{user-site.url}}}', 'buddypress' ),
/* translators: do not remove {} brackets or translate its contents. */
'post_content' =&gt; __( "Thanks for registering!\n\nTo complete the activation of your account and site, go to the following link: &lt;a href=\"{{{activate-site.url}}}\"&gt;{{{activate-site.url}}}&lt;/a&gt;.\n\nAfter you activate, you can visit your site at &lt;a href=\"{{{user-site.url}}}\"&gt;{{{user-site.url}}}&lt;/a&gt;.", 'buddypress' ),
/* translators: do not remove {} brackets or translate its contents. */
'post_excerpt' =&gt; __( "Thanks for registering!\n\nTo complete the activation of your account and site, go to the following link: {{{activate-site.url}}}\n\nAfter you activate, you can visit your site at {{{user-site.url}}}.", 'buddypress' ),
'args' =&gt; array(
'multisite' =&gt; true,
),
),</pre>
&nbsp;

<strong>Por</strong>
<pre>'core-user-registration' =&gt; array(
/* translators: do not remove {} brackets or translate its contents. */
'post_title' =&gt; __( '[{{{site.name}}}] Activate your account', 'buddypress' ),
/* translators: do not remove {} brackets or translate its contents. */
'post_content' =&gt; __( "Thanks for registering!\n\nTo complete the activation of your account, go to the following link: &lt;a href=\"{{{activate.url}}}\"&gt;{{{activate.url}}}&lt;/a&gt;", 'buddypress' ),
/* translators: do not remove {} brackets or translate its contents. */
'post_excerpt' =&gt; __( "Thanks for registering!\n\nTo complete the activation of your account, go to the following link: {{{activate.url}}}", 'buddypress' ),
),
'core-user-registration-with-blog' =&gt; array(
/* translators: do not remove {} brackets or translate its contents. */
'post_title' =&gt; __( '[{{{site.name}}}] Activate {{{user-site.url}}}', 'buddypress' ),
/* translators: do not remove {} brackets or translate its contents. */
'post_content' =&gt; __( "Thanks for registering!\n\nTo complete the activation of your account and site, go to the following link: &lt;a href=\"{{{activate-site.url}}}\"&gt;{{{activate-site.url}}}&lt;/a&gt;.\n\nAfter you activate, you can visit your site at &lt;a href=\"{{{user-site.url}}}\"&gt;{{{user-site.url}}}&lt;/a&gt;.", 'buddypress' ),
/* translators: do not remove {} brackets or translate its contents. */
'post_excerpt' =&gt; __( "Thanks for registering!\n\nTo complete the activation of your account and site, go to the following link: {{{activate-site.url}}}\n\nAfter you activate, you can visit your site at {{{user-site.url}}}.", 'buddypress' ),

),
</pre>
&nbsp;

Luego te recomendaría que instales el plugin <a href="https://es.wordpress.org/plugins/wp-mail-smtp/">WP Mail SMTP</a> y en dirección del remitente puedas colocar un gmail u otra dirección, siempre y cuando haciendo los tests funcione. Para los test prueba con correos que sean de un dominio propio, tipo @comunicacionabierta.net.