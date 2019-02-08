---
ID: 1955
post_title: >
  Guía de Git para comunicadores,
  organizaciones sociales y cocineros en
  general
author: danicotillas
post_excerpt: ""
layout: post
permalink: >
  https://comunicacionabierta.net/2017/02/git-comunicadores-sociales/
published: true
post_date: 2017-02-13 14:52:30
---
[caption id="attachment_1956" align="alignright" width="309"]<a href="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/branching-illustration@2x.png"><img class=" wp-image-1956" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/branching-illustration@2x.png" alt="" width="309" height="199" /></a> Si de inicio entiendes esta imagen entonces este post seguramente no sea para ti.[/caption]
<h2>¿Git... Qué?</h2>
<b>Git</b> (pronunciado "guit" ) es un software de control de versiones diseñado por Linus Torvalds, pensando en la eficiencia y la confiabilidad del mantenimiento de versiones de aplicaciones cuando éstas tienen un gran número de archivos de código fuente.
<h2>Vale, de nuevo... ¿Qué?</h2>
Este suele ser uno de los problemas por los que herramientas como Git no acaban siendo usadas por quienes, en realidad, le sacarían un jugo tremendo: <strong>el lenguaje</strong>. Si, es difícil explicarlo de otro modo... pero no imposible. En el momento en que logremos, poco a poco, empezar a explicar por analogías mucho de lo que ocurre en internet en el lado de la programación, el código, lo hack y lo geek, seguro que empezaremos a abrir un camino aún inexplorado pero siempre deseado. Tanto para el bien del desarrollo colaborativo, como para el enriquecimiento de miradas por distintos grupos que puedan estar interesados, tomemos el reto.
<h5>Permitirme la osadía de intentar dar <strong>otro tipo de definición</strong>:</h5>
<strong>Git</strong> es un programa que permite, a quien desee, aportar nuevas ideas a una idea ya existente de forma colaborativa. Todo ello a través de un sistema de control y revisión que permite que puedas elegir si alguna de esas ideas propuestas mejoran la tuya, descartarlas, volver atrás si la acepté y me arrepentí, mezclar posibilidades y hacer las tuyas propias.

<strong>¿Todavía estás buscando a Wally en la ecuación?</strong> Vamos a ir un paso más allá e intentar contar lo que podrías hacer con Git como si de la preparación de un plato se tratase y trabajásemos entre varios cocineros.
<h3>Antes un poco de contexto...</h3>
<a href="https://git-scm.com/"><img class="wp-image-1957 alignleft" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/git-logo.png" width="153" height="64" /></a>Si te interesa saber cómo nace Git y de qué se trata desde un punto de vista técnico, lo vas a encontrar en <a href="https://git-scm.com/">la página oficial</a> ... con ese bonito lema de "Lo distribuido en la nueva centralización"

Y mira si <a href="https://try.github.io/levels/1/challenges/1">tienes 15 minutos y quieres aprender </a>Git (in english) pues también todo tuyo en modo crudo.

Las plataformas más conocidas donde podemos utilizar Git son: <a href="https://www.github.com">GitHub</a>, <a href="https://www.gitlab.com">GitLab</a> y <a href="https://bitbucket.org">BitBucket</a>. También podemos instalar Git en nuestro propio servidor y no necesitar plataformas de terceros... pero eso para otro día.

Particularmente <a href="https://github.com/danicotillas">uso github</a>, una tremenda red desde donde poder compartir tus códigos (esos conjuntos de instrucciones donde le decimos a un programa qué hacer, o a una web qué información mostrarnos), aprender de otros, leer, estudiar, seguir aprendiendo y sobre todo, conectar desde el hacer.
<h2></h2>
<img class="aligncenter size-full wp-image-2003" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/portada-manual-git.jpg" alt="" width="2048" height="1072" />
<h2><strong>Metámonos en la cocina</strong></h2>
Olvídate de códigos, palabras que suenan raro en tu cabeza, símbolos que nunca viste antes y demás jerga que te hacen cerrar la pestaña del navegador despavorido.

Imagínate que <strong>una chef te invita a su cocina</strong>. Una en la que no sólo puedes darte una vuelta, mirar y ya está: se te permite leer sus libros de recetas de primera mano y conocer todos sus secretos. Y mejor todavía, la cocina cuenta <strong>con un sistema Git</strong> por el cuál tu puedes realizar <strong>sugerencias de mejora</strong> de estas recetas, <strong>copiártelas</strong> y <strong>llevártelas</strong> a tu cocina digital, <strong>continuar mejorándolas</strong>, <strong>practicar</strong>... pero sin la posibilidad de cambiar aquello que planteaba la chef de inicio en su receta, a no ser que te lo permita.

<img class="alignright size-medium wp-image-1981" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/al-dente-bd-300x200.jpg" alt="" width="300" height="200" />Has ido de visita con unas cuantas personas igual de curiosas que tú y han descubierto una fabulosa receta: <strong>cómo hacer pasta</strong>. La receta consiste en la forma de producción completa de la pasta hasta que está lista para hervir. La receta acaba cuando la hierve y la sirve en el plato. El aspecto vendría a ser una cosa parecida a la foto... <strong>¿Yummy?</strong> Si eres de los que crees que le falta algo veamos qué puedes plantear...

&nbsp;

<hr />

<h2>GLOSARIO de un RECETARIO COLABORATIVO</h2>

<hr />

<h3><img class="alignleft size-full wp-image-1982" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/repositorio.png" alt="" width="100" height="100" />Repositorio<a href="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/repositorios-danicotillas.jpg"><img class="alignright wp-image-1983" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/repositorios-danicotillas-226x300.jpg" width="186" height="247" /></a></h3>
El corazón de cualquier cocina, el lugar donde guardamos nuestras recetas. Un repositorio es cada una de ellas, de forma que podemos acceder para leerlas y estudiarlas. En nuestro repositorio guardamos las nuestras, pero cuando vamos al repositorio de otras chefs podemos realizar varias acciones, desde ponerles una estrella de <em>favorito</em> hasta copiárnoslas en nuestro repositorio para desde ahí plantear los cambios que queramos, eso es, hacer <strong>un fork</strong>.

&nbsp;

<hr />

<h3><img class="alignleft size-full wp-image-1974" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/fork.png" alt="" width="100" height="100" />Fork</h3>
Como no quieres estropearle la receta a la chef y prefieres practicar en tu propia cocina sin tener que esperar su aceptación, metes literalmente el tenedor (fork) y le sacas la receta de hacer pasta. Una vez en tu cocina tienes total libertad para probar todas las variables posibles. Que si ahora tomate, que luego queso, que me arrepiento y le quito el tomate, tal vez sea mejor con crema. Planteamos cambios en nuestra propia receta (commits &amp; push) y cuando hemos dado con lo que realmente queremos proponer a la chef le enviamos una propuesta (pull request). Además, si me arrepiento, siempre puedo volver atrás ya tengo la receta inicial sobre cómo hacer pasta.

<a href="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/forked-receta-pasta.png"><img class="aligncenter wp-image-1978 size-full" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/forked-receta-pasta.png" width="1265" height="329" /></a>

&nbsp;

<hr />

<h3><img class="alignleft size-full wp-image-1968" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/commit.png" alt="" width="100" height="100" />Commit</h3>
Decides innovar y lanzarte a la piscina... ¡Crees que estará mejor con albahaca!. Pero tus amigas y amigos no están de acuerdo contigo. Unos creen que mejor tomate, otros que aceite, otros tocino y los más iconoclasistas quieren colocarle piña (¡a la hoguera!).

Cada uno de estos cambios realizados por nuestra parte <strong>es un commit</strong>. En nuestra receta aparecen así pero la receta maestra no ha sido modificada.

&nbsp;

<hr />

<h3><img class="alignleft size-full wp-image-1969" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/push.png" alt="" width="100" height="100" />Push</h3>
Para poder hacer que los cambios en la receta tengan efecto debemos hacerlos públicos. Con el commit ya hemos hecho la solicitud de inclusión, el push es la acción por la cuál los cambios pasan a formar parte de la receta. En nuestras propias recetas (repositorios) hacer un commit y push van acompañados de la mano. Si quisiéramos hacerlo desde la receta de la chef invitada a la que hicimos un fork, sólo ella podrá aceptar los cambios haciendo un push desde la solicitud de cambio. Y esa solicitud se llama pull request, ¿y eso es...?

&nbsp;

<hr />

<h3><img class="alignleft size-full wp-image-1970" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/pull.png" alt="" width="100" height="100" />Pull request</h3>
Queda pendiente que la chef revise y acepte si es que alguna de esas propuestas realmente mejora su receta de pasta. Ella será quién le ponga la albahaca, el aceite, el tocino o la piña, y en qué medida. Estas propuestas son probables peticiones de cambio. Cada una de ellas aparecen como <strong>pull request</strong> para cambiar la receta original (el código fuente).

La chef acepta finalmente la idea de la albahaca después de probarla antes. Agarra el bote y le mete de lleno... Acaba de hacer un pull. Parece buena, continuamos. O tal vez pasado el tiempo se arrepiente, ¡qué dilema!. Como anotó en la agenda (control de revisiones) el momento en que la puso, siempre puede volver al punto de inicio.

[gallery type="thumbnails" columns="4" link="none" ids="1996,1997,1998,1999"]

&nbsp;

<hr />

<h3><img class="alignleft size-full wp-image-1972" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/issue.png" alt="" width="100" height="100" />Issue</h3>
Cuando hemos estado leyendo la receta nos han surgido muchas dudas, hay un punto entre la ebullición del agua y el momento en que se mete la pasta que no nos queda claro. Entonces, podemos <strong>hacer preguntas sobre estas dudas que tenemos a través de los Issue.</strong> De esta forma mantenemos un diálogo, tanto entre la chef y yo, como con todas aquellas personas que han querido echar un ojo a la misma receta y tal vez tengan otras soluciones posibles. La cuestión no es arreglarlo entre dos, sino ¡entre todos los que quieren compartir!

&nbsp;

<hr />

<h3><img class="alignleft size-full wp-image-1971" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/branch.png" alt="" width="100" height="100" />Branches</h3>
Nos hemos metido varias personas al mismo tiempo a ver cómo podemos mejorar la receta. Estar trabajando todas al mismo tiempo, sobre los mismos <em>paso a paso</em> (el código) se puede convertir, y lo hace, en un desmadre. Entonces, hacemos una copia temporal desde la misma receta para tomar un camino alternativo, que puede acabar en algo que se sume finalmente a la receta final, o tal vez no. Estos caminos múltiples son las branches (ramas) y nos permiten estar modificando distintas partes de la receta al mismo tiempo por varias personas. Una vez tenemos certeza sobre el buen devenir de nuestra <em>branch</em>, ¿qué hacemos? Pues fusionarlas, es decir, un merge :).

&nbsp;
<h2>Ahora, mejoremos esta receta usando Git</h2>
Esta guía no será ni mucho menos la mejor que encontrarás, e incluso puede que la sientas bastante incompleta. ¿Echas una mano para mejorarla?

<a href="https://nodocomun.github.io/manual-git"><img class="alignleft wp-image-1988 size-medium" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/octocat-chef-1-262x300.png" width="262" height="300" /></a>Desde <a href="https://comunicacionabierta.net">Nodo Común</a> se ha creado un repositorio donde está esta receta, la:
<h3><strong><a href="https://nodocomun.github.io/manual-git">Guía de Git para comunicadores, organizaciones sociales y cocineros en general</a></strong></h3>
Para poder hacerlo necesitarás justamente poner en juego la terminología que aquí te viene, al tiempo que pruebes, metiendo las manos en la masa, cómo funciona la lógica git y la plataforma de GitHub.

También puedes <em>meterle el tenedor </em>desde el código fuente aquí: <a href="https://github.com/nodocomun/nodocomun.github.io">https://github.com/nodocomun/nodocomun.github.io</a>

&nbsp;

<hr />

<a href="https://nodocomun.github.io/paginas-github/"><img class="wp-image-1994 size-medium alignright" src="https://www.comunicacionabierta.net/wp-content/uploads/2017/02/github_pages-300x112.png" width="300" height="112" /></a>También puedes plantearte <strong>iniciar con tu propia página</strong> en GitHub, para ello hemos traducido la web oficial por si no entiendes bien el inglés:
<strong><a href="https://nodocomun.github.io/paginas-github/">https://nodocomun.github.io/paginas-github/</a>.</strong>

&nbsp;
<h6></h6>
<h6></h6>
<h6>Créditos:</h6>
<a href="https://www.flickr.com/photos/handles/2885877669/in/photolist-5p1STx-7auq8Q-gS61e1-2reptS-5bb85F-5RHrxo-5NNzdy-5NJfuc-8ScMC1-5ovHiP-ckv19C-8A1tYB-q6HBB8-nGxrU4-49NmoE-68umhP-4c5Cd-dSZrLi-a57Hr8-8SX4ob-2fF1TU-6ApWA4-5RHsa3-6ybQNz-dUJp8K-77wKJF-6NfXwf-9qGsPK-ceLqy1-6e8oh2-6HTYun-8gBDiJ-9fq9YQ-7bJRvT-6M9iuT-4yrYok-7soNma-5ryS4d-RbCEPj-72e5kD-aCowmw-4LsWSN-9WQT1s-6wZxQf-6i8wAV-5q4ezF-Zpcts-6mSeCN-4oRBgG-4U24An">Al dente</a> por Handles | <a href="https://creativecommons.org/licenses/by-nc-nd/2.0/">BY NC ND</a>

<a href="https://www.flickr.com/photos/dishingupdelights/7785680550/in/photolist-cRZDzy-mUYoMc-64iwPd-a8xsw9-RSv3vT-mGRuko-bsUr2L-8s8eBL-9HH7Xr-cRZtrE-4VtBgc-7Jq8bA-8hqoVu-e313XS-7CQAde-5ys6o8-9T96Qb-Rmu7eW-8QDdQV-4ZSAdn-54kuG4-5ucy55-4yJVUA-9ai3Gy-9iJxmH-5ASzNL-cwHz9G-hY7r84-eFuVru-5sHGT2-a57Hpe-5p1STx-gS61e1-5eY5K5-2reptS-5bb85F-5ovHor-dNS3hT-5SWyAc-7uFkrq-7JiwTX-2UdZeZ-7auq8Q-2fF1TU-77wKJF-RqpHKw-6HTYun-7bJRvT-4LsWSN-nGxrU4">Spaghetti with Stuffed Roasted Tomatoes and Bacon</a> de esimpraim | <a href="https://creativecommons.org/licenses/by-nc-nd/2.0/">BY NC ND</a>

<a href="https://www.flickr.com/photos/roolrool/4679567207/in/photolist-88w1ie-6Y1nZ9-brcYHT-2Ec9NC-3rbv36-8eP6cW-brdbSP-7ptDyc-eFuVBC-iaESNy-eFuVF5-8JLPhe-8ag9VV-iaESh3-dD6TYd-7rykRT-7Ai8hs-dChbsz-nFGfft-6cxzfU-brfHao-8jr57w-9FDGTz-5uY7EW-8hDjTF-bqgdRg-s25Mon-83uVKy-7wGwrT-4UDeSw-9e7xBX-dXWEUT-4j7TzA-b6vjw6-8tRJ6K-3b4a3G-88ys3p-8hDjne-nktPMk-3TXpok-QQT1hx-8jnQze-62xDPG-9ca3G6-4Jtu16-9m9hdo-7Akbcb-81a2As-QA6urz-56catX">Spaghetti</a> de Rool Paap | <a href="https://creativecommons.org/licenses/by/2.0/">CC BY</a>

<a href="https://www.flickr.com/photos/gaku/4596258746/in/photolist-81a2As-QA6urz-56catX-88ysuK-dXWF2X-4osg33-fALqWG-5Tu3dJ-6myCdv-cRZDzy-mUYoMc-64iwPd-a8xsw9-RSv3vT-mGRuko-bsUr2L-8s8eBL-9HH7Xr-cRZtrE-4VtBgc-7Jq8bA-8hqoVu-e313XS-7CQAde-5ys6o8-9T96Qb-Rmu7eW-8QDdQV-4ZSAdn-54kuG4-5ucy55-4yJVUA-9ai3Gy-9iJxmH-5ASzNL-cwHz9G-hY7r84-eFuVru-5sHGT2-a57Hpe-5p1STx-gS61e1-5eY5K5-2reptS-5bb85F-5ovHor-dNS3hT-5SWyAc-7uFkrq-7JiwTX">Tarako Spaghetti</a> de Gaku | <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC BY SA</a>

<a href="https://www.flickr.com/photos/dippy_duck/4227363401/in/photolist-7rykRT-7Ai8hs-dChbsz-nFGfft-6cxzfU-brfHao-8jr57w-9FDGTz-5uY7EW-8hDjTF-bqgdRg-s25Mon-83uVKy-7wGwrT-4UDeSw-9e7xBX-dXWEUT-4j7TzA-b6vjw6-8tRJ6K-3b4a3G-88ys3p-8hDjne-nktPMk-3TXpok-QQT1hx-8jnQze-62xDPG-9ca3G6-4Jtu16-9m9hdo-7Akbcb-81a2As-QA6urz-56catX-88ysuK-dXWF2X-4osg33-fALqWG-5Tu3dJ-6myCdv-cRZDzy-mUYoMc-64iwPd-a8xsw9-RSv3vT-mGRuko-bsUr2L-8s8eBL-9HH7Xr">Meatballs &amp; Spaghetti</a> de Matt | <a href="https://creativecommons.org/licenses/by-nc/2.0/">CC BY NC</a>