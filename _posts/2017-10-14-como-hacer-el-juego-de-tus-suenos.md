---
layout: post
title: "Como hacer el juego de tus sueños, publicarlo y no morir en el intento"
categories:
  - Software
  - Juegos
tags:
  - juegos
---

##### Esta es una traducción del artículo original de Juan Linietsky en [Godot Engine](https://godotengine.org/article/how-actually-make-your-dream-game).

---

---

<img rel="image_src" src="https://godotengine.org/storage/app/uploads/public/598/fb6/1bb/598fb61bb576f136583931.png" alt="">

### MOTIVACIÓN

Hoy estoy
reinstalando mi computador de desarrollo, así que no puedo programar mucho que digamos. Compilar Godot toma cada vez más tiempo, así
que supongo que una nueva configuración es una forma más de
acelerar el desarrollo de Godot.

La motivación para
este artículo es que muchos desarrolladores me pidieron escribirlo desde hace tiempo. Sin contar que soy el desarrollador líder de Godot,
tengo casi 20 años de experiencia desarrollando y entregando juegos,
y una década de experiencia como consultor técnico.

Generalmente mi
responsabilidad abarcaba desde programador hasta tener mis propios
proyectos, pero la mayor parte del tiempo como director técnico o
consultor técnico.

También tuve varias
compañias y ayudé a otros en la parte de negocios así que creo
tener una imagen bastante clara de todo el proceso (Lo cual no
significa que es a prueba de fallas, nunca lo es).

No me hice rico (aún
:D) haciendo juegos, pero aprendí bastante en el proceso... y hoy
en día disfruto desarrollando Godot más que cualquier otra cosa.

Estoy seguro que
otras personas han escrito sobre el mismo tema, pero este artículo
está escrito desde mi propia experiencia, con la esperanza de que
sea útil.

Desde que Godot fue
lanzado, ví muchos desarrolladores trabajar en proyectos asombrosos
con él. La fortaleza más grande de Godot es que, gracias a su
diseño, facilita el hecho de arrojar código que simplemente
funciona (Y que se escala a grandes proyectos) sin tener que
preocuparse acerca de la arquitectura del juego. Mucho juegos fueron
lanzados, pero una gran cantidad fueron abandonados.

Intenté contactar a
varios de los desarrolladores para preguntarles cuales fueron las
razones y en la mayoría de los casos, estas no eran técnicas, sino
relacionadas con que el alcance del proyecto era demasiado difícil de
manejar.

### HACER JUEGOS ES MUY DIVERTIDO, PERO MUY DIFÍCIL

Desarrollar juegos _es difícil_, cubre bastantes disciplinas pero no puede tomar prestado
mucho de sus procesos.

Del lado artístico
y creativo, artistas (ilustradores, músicos, escritores) usualmente
conceptualizarán algo y después añadirán profundidad a ese algo.
En el desarrollo de videojuegos, tu implementación inicial del
gameplay siempre está rota y necesita constante arreglo para
mejorar. En muchas situaciones, es simplemente imposible que funcione,
y darse cuenta que debe ser abandonada en favor de otra cosa es una
decisión muy díficil de tomar.

Desde el lado
técnico, los procesos enseñados en la universidad generalmente no
se pueden aplicar. La ingeniería de software está basada en listados de
requerimientos y a partir estos se desarrollan casos de usuario. A partir
de los casos de usuario se conceptualizan todas las interacciones.
Esto no funciona en la programación de videojuegos, porque estás
más enfocado en como se siente el jugador que en lo que él o ellá
harán.

### PATRONES DE DISEÑO, O LA FALTA DE ESTOS

Incluso aplicando
patrones de diseño estándar no está garantizado que funcionará.
Una situación que he visto repetirse una y otra vez como consultor
es tener que lidiar con ingenieros que se mienten a sí mismos acerca
de aplicar exitosamente MVC a su arquitectura de juego (y haciendo un
plato completo de espagueti y albóndigas como resultado). Otro caso
es de ingenieros alegando haber encontrado el éxito al no usar el modelo OOP (mientras que de una forma u otra sí lo están usando,
sin darse cuenta o admitirlo). Lo he visto tantas veces que no puedo
contarlo con los dedos.

Esto coincide con
otra situación que he visto incontables veces, la cual es
programadores preocupandose demasiado de "hacer las cosas
correctamente" y de "buenas prácticas". A menudo esto
resulta en código con exceso de encapsulamiento, lo cual a su vez
resulta en bases de código que se convierten en un dolor de cabeza
al modificar cuando sus especificaciones cambian.

Si estás
escribiendo un videojuego, solo escribe tan rápido y simple como
puedas. No molestes con diseño, no apliques patrones o
encapsulamiento solo por hacerlo, hazlo rápido y sucio y solo **hazlo
funcionar**. Si estás planeado tener código limpio en algún punto,
tiene que ser porque se ha vuelto muy difícil trabajar con él, de lo
contrario no lo toques.

Una excusa común
para lo anterior son equipos de trabajo y muchos programadores
trabajando en un juego. Los programadores en jefe requieren código
limpio y organizado, lo que resulta en un desarrollo muy lento. La
lógica detras de esto es "Debemos ser capaces de reemplazar
programadores en cualquier momento, así que el código debe ser
inteligible y mantenible". En realidad, toma mucho más tiempo
desarrollar de esta forma y difícilmente se logra reducir costos en el largo
plazo.

Solo deja claro que
cada programador en el equipo tiene un papel claro y área de
responsabilidad. Déjalos trabajar de la forma que les guste, rápido
y sucio, pero solo asegúrate de que escriban APIs limpias para
comunicar con otros programadores. Lo que pierdes en organización lo
ganas en órdenes de magnitud con la velocidad de desarrollo.

Cuando trabajo con
Godot, me aseguro que el diseño y la arquitectura son tan perfectos
como sea posible. Cuando trabajo en un videojuego, lo que quiero es
tener las cosas hechas lo más rápido posible.

En este punto, mucho
lectores pueden haber notado que Godot fue creado para desarrollar
videojuegos de esta manera. Godot fomenta la productividad por encima
de todo en su diseño. La manera en que el sistema de escenas trabaja
permite aplicar la fórmula "divide y vencerás" para
desarrollar juegos (en lugar de preocuparse por nimiedades como
MVC, subdivisión en componentes, etc.) La simplicidad de GDScript
permite escribir grandes porciones de código que
"simplemente funcionan" y una vez lo hacen, nunca los tocas
de nuevo. Alcanzar ese "sentimiento" de que las cosas
encajan perfectamente fue algo en lo que Ariel y yo trabajamos con
los años, antes de que Godot fuera libre y abierto.

Esto es también por
lo que nos esforzamos tanto desarrollando Godot, a pesar de que aún
faltan muchas cosas, sabemos que tenemos algo especial que nadie ha
hecho antes.

### EL MOTOR NO ES SUFICIENTE, LO QUE IMPORTA ES COMO HACES FRENTE AL DESARROLLO

Una de las preguntas
que más aparecen en la mayorías de redes sociales es "Quiero
hacer X tipo de juego, ¿Que motor es mejor para ello?" Tanto
como un motor puede ayudar en un caso específco de uso, la verdad es
que el éxito depende sobre todo de cúan factible tu proceso de
desarrollo es.

El primer gran error
de la mayoría de los desarrolladores es empezar con un arte
espectacular haciendo un simple prototipo y esperar desarrollar el
resto del juego de la misma manera. Con el tiempo un número de
situaciones muy probablemente surgirán:

- Los _assets_* están OK,
	pero el gameplay apesta. Sientes como que empezar todo de nuevo es
	lo mejor, pero esto también es desmotivante debido al tiempo
	invertido. 
- El juego está OK, pero la ves
	que los _assets_ podrían haber sido mejor y crearlos de
	nuevo is desmotivante 
- El juego va bien, pero sientes
	que muchas cosas podrían ser implementadas y crear _assets_
	para todo eso se siente más como un obstáculo en este punto,
	hacerlo resulta realmente desmotivante. 
- Para que el juego se haga, aparece la necesidad de obtener
	inversión debido a complejidad inesperada. 

###### * _assets_, en el ámbito de videojuegos significa: Cada uno de los elementos que componen el juego (animaciones, modelos, IA, sonidos, etc), N. del T.

---
Estos son escenarios comunes y la razón
por la cual la mayoría de proyectos fracasan. Estoy seguro que
muchas de ellas suenan bastante familiar. !Empecemos de nuevo el
proceso y hagámoslo bien esta vez, desde la conceptualización hasta
la publicación!

### EMPEZANDO DE NUEVO, ¿EL JUEGO ES VIABLE COMERCIALMENTE?

Espera, ¿No debería venir un
prototipo primero? Despues de una idea la acción más natural es
prototiparla...

Bueno no en realidad. Aquí es donde
99.99% de los desarrolladores independientes y estudios cometen su
primer y más fatal equivocación.

No, no es la amplitud lo que hace que el
juego sea viable o inviable, muchos de los artículos que lees sobre
hacer un juego exitoso te dirán que mantengas tu amplitud reducida
para evitar riesgos, este es un consejo malo e inexperto, no lo
sigas, sin riesgo no hay ganancia en este mundo. La clave es
comprender cómo gestionar este riesgo.

Solo plantea la amplitud que quieres.
Será el proceso de desarrollo en sí mismo el que revelará, según
tus fortalezas y limitaciones, cuáles son tus límites. La ambición
es necesaria para tener éxito, no cortes tus alas temprano.

Antes de prototipar, debes ser capaz de
responder las siguientes cuatro preguntas:

- ¿Quién jugará el juego? 
- ¿Cómo llegarás a los
	jugadores objetivo? 
- ¿Cómo se financiará el
	desarrollo? 
- ¿Qué hace que tu juego sea
	diferente? 

Elaborado a continuación:

#### 1) ¿QUIEN JUGARÁ EL VIDEOJUEGO?

Esta es la primera
pregunta que debes hacerte a ti mismo. Solo trata de imaginar quien
va a jugar el juego. Respuestas comunes a esta pregunta son:

- Todo el mundo, ej: Este juego es
	un buen puzzle, tower defense, casual, etc. 
- Una audiencia principal, ej:
	RPG, FPS o un juego de estrategia. 
- Una audiencia nicho, ej: Un
	juego de aventura, un juego basado en turnos, etc. 
- Juegos Indie, ej: Gente buscando
	algo genial, juegos pequeños, no importa el tipo. 
- etc. 

Solo intenta entenderlo bien
antes de continuar con la siguiente pregunta, la cual es:

#### 2) ¿COMO ALCANZARÁS A TUS JUGADORES OBJETIVO?

Aquí es donde las cosas empiezan a
ponerse difíciles. Desarollemos los casos que mencionamos arriba:

**Un juego casual:** Los juegos
simples y casuales (como angry birds, 2048, runners, etc) a menudo
los juega todo el mundo. Sí, su mercado es grande, billones de
jugadores son tus clientes potenciales... así que, solo lo haces,
lo publicas y ¿Voilá? No realmente, las tiendas de juegos están
tan saturadas que cualquier cosa que publiques inmediatamente pasará
desapercibida.

La publicidad para los juegos móviles
está fuera de cuestión, es demasiado costosa. Puedes conseguir una
distribuidora, pero la mayoria de las distruidoras son tramposas. Si te
dicen que ellas gentilmente van a publicar tu juego, ¡No les creas!
Solamente van a lanzar tu juego con banners que apuntan a sus juegos
(que en realidad hacen dinero) via cross-promoción. Sí, ellos
lanzarán tu juego y lo usarán para su propio beneficio, no el tuyo.

Las verdaderas distribuidoras te harán
esta pregunta: "Cuales son tus KPIs?" o más como "¿Cuales
son las tasas de conversión y de retención de tu juego?" ¡Esa
es una verdadera distribuidora móvil! Aquella dispuesta a invertir dinero
en tu juego.

Desafortunadamente esta es una pregunta
muy difícil de reponder positivamente. Para darte una idea, la manera
más popular de hacer dinero en el entorno móvil es vía
free-to-play (alias "Compras dentro de la app"). Cualquier
otra cosa no funciona. Juegos pagos (gratis o con pared de pago) no
hacen dinero y los banners hacen tan poco dinero que no es siquiera
suficiente para sobrevivir (incluso si obtienen millones de
descargas). Sí, el único camino para el éxito económico es hacer
tu juego free-to-play, lo que significa que la descarga es gratuita
pero el contenido del juego es vendido al jugador para a) hacer el
juego más sencillo y b) conseguir estupendas opciones de
personalización.

Lo siguiente es bastante complejo de explicar y
va más allá del alcance de este artículo, pero la idea es que, en
el modelo free-to-play, los "jugadores" (llamados
"usuarios" en el mercado) necesitan ser comprados. Hay
compañias que por, digamos USD$5, te consiguen _un_ usuario
para jugar tu juego. No es una broma y generalmente cuesta mucho más
que USD$5. Esto incrementa considerablemente el ingreso promedio por
usuario.

El término "conversión"
significa en promedio cuanto puedes ganar por jugador, por monto
gastado en el juego. Si gastas USD$5 por jugador, pero obtienes USD$8 en
promedio, tienes una tasa de conversión positiva de 1.6. Una vez
tienes una tasa de conversión positiva, tu juego literalmente se
convierte en máquina de imprimir billetes.

Aquí es donde puedes encontrar
fácilmente productores para invertir en UA (abreviación de
"adquisición de usuario", o solo compra de usuarios para
ti por una parte de %). No es necesario decir que llegar a este punto
es increiblemente difícil sin suficiente inversión y este tipo de
juegos duran años en desarrollo, y en pérdidas, mientras se ajusta su tasa de conversión
hasta ser positiva.

Para ser breve, tus oportunidades de éxito en móviles con juegos casuales son de escazas a
inexistentes (aunque de vez en cuando ocurren milagros). Simplemente
no lo hagas excepto si es por diversión y/o aprendizaje.

Expertos en marketing siempre te dirán
que, contrario al sentido común, cuanto más amplio sea el mercado,
más difícil es de alcanzar.

**Un juego convencional (mainstream):** Estos juegos venden con un montón de inversión en publicidad
para llegar a sus usuarios (y también cuesta bastante crearlos). Si
tienes suficiente experiencia desarrollando videojuegos, puedes
intentar irte por esta ruta.

**Un juego de nicho:** Los nichos
generalmente son fáciles de llegar. Son sitios dedicados, foros,
grupos de facebook, etc. También hay productores especializados en
cada género (ej: juegos de estrategia basados en turnos, aventura,
etc.), que pueden decirte los numeros a los que ellos llegan si preguntas.

**Un Indie o juego experimental:** Steam,
GOG, etc. aún son buenos lugares para estos juegos, siempre y cuando
tu juego sea lo suficientemente interesante (más de eso en la
pregunta 4). Ten en cuenta que la mayoría de los juegos o se venden
o no lo hacen, no hay punto medio al que puedas aspirar.

#### 3) COMO SE VA A FINANCIAR EL DESARROLLO

Necesitas pensar acerca de como el
juego deberá ser financiado. Debajo explicaré cuales son la
aproximaciones más comunes para obtener fondos.

**Distribuidoras:** Puedes encontrar
financiación de distribuidoras relativamente fácil si sigues los
siguientes pasos (esto es porque casi nadie lo hace... pero ten
seguro que va a ser explicado en las secciones siguientes).

La forma más común es que las
distribuidoras te den un adelanto en ventas y también tomen una
rebanada. Solo verás dinero despues de que la productora recupere su
adelanto (este es el típico retorno a la inversión).

Cuando busques distribuidoras, intenta
buscar juegos similares al tuyo y mira quien los publicó. En
general, ellos entienden el mercado mejor y estarán más capacitados
para valorar los riesgos de tu título.

**Crowdfounding:** Sitios como
kickstarter, Indiegogo o Patreon son considerablemente difíciles hoy
en día para obtener fondos (La siguiente pregunta te ayudara en
esto). Una estrategia común es pedir mucho menos dinero (Y ofrecer
un juego más pequeño) y luego, si es exitosa, ve con una productora
o inversionista privado y muéstrales tu éxito (básicamente, que la
gente está interesada en tu juego) y así consigues el resto del
dinero necesario.

**Subsidios:** Revisa con tu
gobierno local , muchos países quieren que su industria crezca, así
que ofrecen subsidios para desarrollo de videojuegos.

**Inversionistas:** Hay
inversionistas especializados en juegos, pero en general están más
interesados en poseer parte de tu compañia o propiedad intelectual.
El tipo más común es capital semilla (más de esto después).

**Ventas en avance y desarrollo de comunidad:** Este es uno de los mejores caminos para financiar el
desarrollo en mi opinión, pero tiene que hacerse correctamente. La
idea es desarrollar tu videojuego y formar un comunidad leal
alrededor de este durante su desarrollo. Debes ser muy bueno en esto,
inclúyelos en el desarrollo y escúchalos. Conforme  la comunidad
crezca, más y más personas van a comprar tu juego por adelantado
hasta el momento en que finalmente esté completo. Tu comunidad
también estará a cargo de dejar que otros conozcan el juego, así
que va a crecer por si mismo.

Finalmente, la pregunta más importante
y difícil de responder

**4) QUE HACE A TU JUEGO DIFERENTE**

Si tu juego no es lo suficientemente
diferente a lo que está ahí fuera (en una forma obvia), fracasará.
La gente no querrá jugarlo, las distribuidoras no estarán
interesadas y ninguna comunidad se formará al rededor.

Lo que hace las cosas peor, tienes que
ser capaz de comunicar ese factor diferencial muy fácilmente y con
una sola frase, imagen o video. Si falla en impresionar, muy
posiblemente fracasará. Si luce similar a otros juegos, muy
probablemente también fracasará. Necesita ser diferente.

La diferencia puede ser con una
concepto innovador de gameplay, o un estilo artístico que no se ha
visto antes en ningún juego. Diseño de personajes únicos también
puede generar interés. Para un RPG o juego de aventura, la historia y
el arte son la clave.

### CREANDO UN PROTOTIPO

Si te sientes seguro de poder responder
las preguntas de arriba, es tiempo de hacer un prototipo. El objetivo
del protipo es probar que tu idea funciona y que la estética (arte,
sonido, etc.) va por buen camino.

He conocido muchos diseñadores que
podrían fácilmente apostar dinero en que sus ideas funcionan, solo
para verlas fallar una vez se han prototipado. Nunca jamás pases por
alto esta etapa.

Tu arte (o sonido) pueden no estar
finalizados en esta etapa. Tu código también puede estar
increiblemente desordenado, eso no es problema. Lo que importaes que
_la experiencia _se sienta asombrosa. Hablando de usabilidad, el
prototipo de sentirse final o cercano a final. Debe expresar tu idea
tanto como sea posible.

Iterar en esta etapa antes de moverse a
la siguientes vital. No dejes ninguna funcionalidad central sin
probar, y continúa haciendo cambios hasta que se sienta casi
perfecto.

Cualquier funcionalidad central que no se
resuelva aquí será un dolor de cabeza para arreglar en el futuro. Esto
significa que los controles deben sentirse fluidos y la acción
gratificante. Debe hacer clic con tu idea.

¡Aquí pide retroalimentación tanto como
sea posible!

Hablando de dinero, la etapa de
prototipado es la mejor para encontrar inversiones de capital
semilla. Este tipo de inversionistas te darán el dinero suficiente
para desarrollar un tira vertical (siguiente sección), y preguntarán
por un trozo considerable de tu ganancias totales (usualmente al
rededor de 30 o 40%).

La lógica detrás de la inversión de
capital semilla es que ellos (los inversionistas) invierten pequeños
montos en una gran cantidad de proyectos de alto riesgo y que no han
sido probados. Si uno de estos es un éxito crucial, ellos hacen una
gran cantidad de dinero.

### REALIZANDO UNA TIRA VERTICAL

Si estás creando un juego entero tu
solo, en tu tiempo libre, o tienes algo de inversión puede no ser
necesario hacer este paso. De lo contrario, este es el paso clave
para asegurar la inversión para todo el juego (o hasta alfa).

La idea de la tira vertical es tener
una pequeña porción de tu juego, pero esta porción debe ser de
_calidad final._

Como ejemplo, si tu juego tiene 30
niveles (misiones, escenas, lugares, etc.), haces 2 o 3 de ellos. Y
deben ser de absoluta calidad final. Incluso referencias al resto del
contenido debe ser visible, no importa si al intentar acceder no
funciona.

No es necesario que sean las primeras
partes del juego, pueden ser secciones aleatorias (aunque una buena
escena introductoria puede resultar muy bien, incluso si es más
difícil de lograr).

¿Porque es la tira vertical tan
importante para obetener inversión? Por las siguientes razones:

#### 1) REDUCE EL RIESGO PARA EL INVERSIONISTA

Invertir tiene todo que ver con
riesgo. A menor riesgo, mayor el chance de obtener inversión. Si un
prototipo muestra que la idea funciona, una tira vertical muestra que
eres capaz de crear el juego entero.

#### 2) HACE QUE LA ESTIMACIÓN DEL COSTO DE DESARROLLO SEA CONFIABLE

Una vez llegados a este punto deberías conocer
cuanto costó y cuanto tiempo tomó hacer la tira vertical.

Hacer una extrapolación es posible: Si
crear 10% del juego (el tamaño de la tira vertical) costó $20k,
puedes estimar que el costo final (100% del juego) estará al rededor
de los $200k.

#### 3) FACILITA AJUSTARSE A DIFERENTES PRESUPUESTOS

Muchas distribuidoras e inversores
puden no tener el suficiente dinero disponible para hacer un juego de
la longitud y contenido que quieres. La tira vertical te permite
extrapolar cuanto contenido necesitarás cortar en orden de ajustarte
al presupuesto disponible.

### DESARROLLAR HASTA ALFA

Aqué es donde la mayoría de los
desarrolladores cometen otro erro fatal. **No** añadas más
_assets_ finales (arte, sonido, etc.) hasta que llegues a la
etapa alfa. Siempre utiliza _placeholders_ en el arte. La
única excepción aquí, si el tipo de juego lo requiere (ej. un
juego de luchas), es animación.

En el juego entero, tal cual, todo el
contenido _debe_ ser desarrollado con _placeholders_(ej.
bocetos burdos, bloques, CSG, etc.).

Yo sé que puede ser muy frustrante,
pues ver cosas convertirse en realidad es enormemente gratificante.
Aún así, como sea, debes resistir la tentación.

Aquí hay algunas razones por las
cuales hacerlo:

#### 1) LA PRIORIDAD ES EL GAMEPLAY

Lo que define tu juego es buen
gameplay. Debe funcionar lo mejor posible, por lo que solo tiene
sentido desarrollar primero todo el contenido. Asegúrate de que
todas las características han sido implementadas y que el juego se
puede jugar desde el inicio hasta el final. Los controles se deben
sentir bien y también la usabilidad.

Poner en orden todos los problemas aquí
es más barato porque el arte no necesita hacerse de nuevo.

#### 2) ALFA ES GENIAL PARA OBTENER FINANCIACIÓN

Alfa es el punto dentro del desarrollo
cuando tienes mayor fortaleza y calma para negociar inversiones y
publicaciones. Esto es porque:

- Puedes mostrar que puedes crear
	todos los assets y sabes cuanto tiempo tomará (gracias a la tira
	vertical). 
- Puedes mostrar que el juego, con
	contenido completo funciona (literalmente puedes jugarlo y mostrar
	que es bueno/divertido/etc.), así que no hay riesgo de que salga
	mal. 
- No has gastado mucho tiempo aún,
	ya que ha sido realizado más que todo con programadores y uno o dos
	artistas/animadores/diseñadores. 
- Una inversión real contratará el resto de los artistas
	(animación, gráficas, musica, efectos, etc.) para finalizar el
	juego. 

Como resultado, el riesgo de desarrollo
se minimiza bastante y facilita la obtenición de un trato mucho
mejor.

### ¡LLÉNALO CON ASSETS, VE HACIA BETA!

Beta es prácticamente finalizar el
juego entero (excepto por bugs y talvez ajustes pequeños y mínimos).
Significa crear todos los assets que hacen falta para completarlo.

Esta etapa es muy gratificante y
divertida, pero es muy dura. Desde una gran compañia hasta un
desarrollador indie en solitario, rellenar el juego con los assets
finales siempre se hace cerca al final del desarrollo.

Para indies, este es el momento
perfecto para contratar alguien que cree el arte, musica, vfx, etc.
Sabes que los requerimientos (y el juego en sí mismo) no van a
cambiar, así que gastarás mucho menos dinero. Serás capas de pedir
presupuestos precisos y firmar contratos espeíficos por el
contenido que debe ser hecho.

Con esto se evita el problema más común
de tener que contratar un artista en bases mensuales y luego quedarte
sin dinero para pagarle porque el desarrollo tomó más tiempo del
esperado.

Tareas típicas alfa-&gt;beta, aparte
de los assets finales, son traducciones, cinemátografías, grabación de
voces, etc.

### ORO

Un juego va a oro cuando todos los bugs
y pequeñas peculiaridades han sido resueltos y el juego se siente lo
suficientemente estable. Esto puede tomar una cantidad de tiempo
considerable, muchos estudios simplemente lanzan el juego antes de ir
a oro y arreglan bugs a través de actualizaciones. Esto apesta,
pero la industria se acostumbró a hacerlo.

### PUBLICACIÓN

Mi experiencia con publicaciones es una
mezcla. Las distribuidoras generalmente apuestan con sus juegos.
Financian muchos proyectos, pero solo invierten realmente (en
promoción) en aquellos a los que les va bien en ventas. Los que no,
rara vez obtienen algo de dinero y se les deja morir. Esta es la ley
de la vida.

Es tal y como lo escuchaste. Incluso si
consigues un trato con una distribuidora, no garantiza que vas a tener
dinero invertido en promoción. La única situación que puede darte
un mejor acuerdo (la distribuidora aceptará gastar hasta cierto
monto en promoción) es acercándose a una distribuidora con un juego
finalizado, o en alfa como mucho.

Al principio, estaba enojado por este
hecho, pero ahora entiendo que es el camino de acción más natural
para una distribuidora. Son compañias, no beneficencias.

Tampoco me malinterpretes, las
distribuidoras marcan una gran diferencia, incluso si no invierten
_dinero_ en promoción, usualmente tiene canales muy bien
lubricados con la prensa y muchas tienen cultos de seguidores (como
Atlus o Daedalic) que comprarán sus juegos. Ellas también conocen
los mercados bastante bien así que incluso si tu juego no se vende,
no significa que no hicieron nada para promocionarlo.

En la mayoría de los casos, encontré
que puedes negociar con la distribuidora el hecho de que te devuelvan
los derechos de publicación si el juego hace menos dinero que
determinado umbral de ganancias... así que existe la posibilidad de
presentarlo en otro lugar. Por supuesto, si obtienes inversión de
una distribuidora, ellos requerirán que la retornes antes de que
esto suceda (Lo cual puede ser negociado con una nueva
distribuidora).

Habiendo dicho eso, mi experiencia en
este campo es que si un juego no se está vendiendo bien, las
probabilidades de que salga mejor con un montón de dinero
arrojado a promoción siguen siendo pocas.

En cuanto a los motores, puedes haber
escuchado que distribuidoras te piden como requisito usar Unity,
Unreal o un motor específico. Esa es una mentira, yo publiqué
docenas de juegos con Godot para consolas, móviles y PC y nunca
nadie cuestionó la tecnología.

El único caso donde puedes llegar a
oír esto es cuando contratas trabajos grandes para propiedad
intelectual de terceros (como Disney, Lego, etc.). Algunos de ellos
te piden el código fuente en orden de realizar cambios sin tu
soporte. Está en tí negociar eso.

**AUTO-PUBLICACIÓN**

Publicarse a uno mismo puede ser
extremadamente difícil. Hacer todo el trabajo de promoción puede
tomar un buen tiempo, incluso si aprendes como hacerlo. Conozco
algunos pequeños distribuidores que hacen el trabajo a cambio de una
parte de las ventas (en pagos mensuales). Aunque me siento más
comodo con los tramposos, solo revisa como se han vendido sus otros
juegos publicados. SteamSpy puede ser una buena herramienta.

**PALABRAS FINALES**

Como puedes ver, el proceso entero de
hacer un videojuego es increíblemente complejo y el éxito no está
garantizado, pero este artículo con suerte te ha llevado a traves de
las partes más importantes del proceso (cualquier realimentación de
aquellos con más experiencia es bienvenida).

Hoy en día, se estima que uno de diez 
juegos que reciben inversión se convierte en un éxito, y solo dos
o tres recuperan la inversión (por supuesto estos datos pueden variar
dependiendo de la fuente...).

Pero si te vuelves bueno en esto, es algo de lo que puedes vivir. Si repites el ciclo de **prototipo/tira vertical/alfa/beta/oro/publicación** la veces suficientes, pienso que
las probabilidades de ser exitoso en tu vida son de hecho muy altas. 

¡Solo no te rindas!