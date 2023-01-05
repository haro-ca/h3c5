---
layout: "../../layouts/BlogPost.astro"
title: "Y empezar el 2023"
description: "Notas de sobre la dificultad de construir productos"
pubDate: "Ene 02 2023"
heroImage: "/empezar_2023.svg"
---

# Una verdad incómoda
Mi 2022 fue raro para alguien que se dedica a datos, y todo comienza porque fui contratado para un proyecto de desarrollo de software a mitades de 2021.  
**El lugar:** un área nueva de un banco, enfocada a productos digitales.  
**El rol:** Coordinador de un equipo pequeño y, en caso de ser necesario, contribuidor individual.  
**El objetivo:** crear una aplicación web para conseguir clientes.  
**La expectativa:** Simple y sencilla, que hubiera aplicación.  
**Spoiler:** Para junio de 2022 fracasé... 
<br></br>
Previo a mi fracaso y, por supuesto, a mi renuncia, yo me encontraba trabajando en _proyectos de datos_<sup class="tm">TM</sup>.  
**Mi primer rol**, fue de **analytics engineer/data analyst**, i.e. análisis _ad hoc_ con python/R sobre información extraída desde una base de datos
(DB de aquí en adelante) analítica, aka DataWarehouse.  
**El segundo** fue en un rol de **ingeniero de datos**, i.e. diseñar e implementar ETLs de una DB transaccional a una DB analítica (por ejemplo, BigQuery).
No prestemos mucha atención a los nombres, en mi cabeza 
los organizo como dbt labs los describe en [esta guía](https://www.getdbt.com/data-teams/analytics-job-descriptions/); pero sí prestemos
a la etapa con la que cada rol lidia dentro de una _cadena de producción_ de un producto de software.
<br></br>

Para darle orden, dibujé el siguiente diagrama:
<img src="/tech_prod_arquitecture.png" alt="diagram of a tech prod arquitecture" width="900" class="center"/>

El **primer rol**, puede ser la barra de analytics engineer (azul), o la de **data analyst (morado)**, pero, 
dado que estaba mucho más en la parte de reporteo (visual) y no tanto en el [modelado dimensional](https://en.wikipedia.org/wiki/Dimensional_modeling) del warehouse, 
centrémonos en esta segunda barra.  
El **segundo rol** es la barra de **data engineer (verde)**. Notar que toca ligeramente el rol de backend, esto es intencional.  
Mi **tercer rol**, el de crear una aplicación web en el banco, lidiaba con todo el cuadro izquierdo, el de ingeniería de software; incluyendo, claro, **ambos backend y frontend.**  
<br>
Es decir, participé en 3 roles diferentes para crear un producto software, los 3 lidiando con distintas secciones de un producto virtual.  
Mi conclusión, y la verdad incómoda: **construir software de valor es sumamente difícil.**

# Una serie de eventos (des)afortunados
Mi entrada al banco fue en septiembre de 2021. Para ese punto yo ya llevaba 4 años en el _data science_<sup>TM</sup> profesional (aka me pagaban)
y unos 5 años interesado en la disciplina.
Mis primeros años, como la mayoría, fui **analista**. Atendía el clásico análisis _ad hoc_, siempre iniciado con la bella oración: "la jefa necesita estos datos para
las 5". Ya saben cómo va esto: query de SQL, limpieza y tablas en python-pandas o r-tidyverse, gráficas en _ggplot2_ (nunca en matplotlib, no soy psicópata), 
y copiar y pegar a una ppt que puede o no que viera la luz.  
Claro que, también como la mayoría, me pregunté **¿qué valor aporta esto?**  
<br>
Eso, más una buena lectura de [Outliers de Gladwell](https://en.wikipedia.org/wiki/Outliers_(book)), motivó mi salida del rol, y de la organización.  
No conscientemente **decidí dedicarme a roles con mejor capacidad de medición del valor agregado** (soy economista por estudios, tenía que meter el término _valor
agregado_ en algún lugar y ahí está por primera vez). Ahora, esto es parte de un fenómeno más grande sobre la ciencia de datos, i.e. es difícil tener impacto 
en un área de datos, y más en el rol de _data scientist_/_data analyst_, 
últimamente se habla mucho de eso: 
[Data teams are still struggling to have impact](https://hex.tech/blog/series-b/), [Goodbye, Data Science](https://ryxcommar.com/2022/11/27/goodbye-data-science/), pero, 
claro, yo en ese momento desconocía todo esto.
<br></br>
**Me dediqué a la ingeniería de datos**, porque es mucho más fácil medirlo que el _data science_: el dato llegó a la tabla o el dato no llegó a la tabla, 
vs. "qué buena historia me contaste con estos datos" (nadie dice eso, pero es una buena caricatura de la estrella de norte de un analista). 
**Logré sentir mayor felicidad por el día a día de mi trabajo**; a su vez, dada la intersección entre ingeniería de datos 
e ingeniería de software backend, logré desarrollar habilidades de código que rara vez son importantes en tareas de datos más _frontend_, menciono algunas: 
buen control de versiones de código y cambios, buen control de ambientes de trabajo local y remoto (dev, qas, prod), _profiling_ de código, 
pruebas unitarias/integración, y vim (me FASCINA vim). También están habilidades de arquitectura: microservicios vs. monolitos, seguridad de APIs, etc. pero 
no quiero alargar esto más, el punto: **aprendí bastante, pero seguí con dudas del valor final del trabajo con datos**.  
<br>
**Ahora podía disfrutar de un ETL bien hecho**, Airflow te marca si un job es exitoso o fallido, así que habla por sí solo. Es más, la DB habla por sí sola, 
si un día no había actualización en una tabla, o un query tardaba mucho, seguramente recibía un Teams ese día preguntando qué había pasado.  
Pero, **había algo que no podía ignorar**, ¿de quién creen que era ese mensaje de Teams? De un analista de datos.  
**Seguía con esa duda, ¿qué valor agregado terminaban realmente generando estos datos?**  
La única diferencia es que ahora sabía qué estaba atrás del query al DataWarehouse, 
pero el downstream de ese query, para mí, seguía siendo un pozo sin fondo.  
<br>
Entra septiembre 2021, algún día contaré la entrevista de trabajo, pero, en resumen, recibí un: **te declaro desarrollador web, ten un equipo, quiero un app en 10 meses.**  
No soy de correr de los retos, y siempre fui honesto en mis entrevistas, sabía bastante de datos y backend, aunque nada de frontend, lo justificaba 
pensando que algo debieron ver en mí para aceptarme a pesar de esto, y, terminé elaborando 
la pregunta inaugural para estrellarse contra una pared de humildad: ¿qué tan difícil podía ser?  
Por encima de todas mis dudas, **se asomaba la oportunidad perfecta para entregar valor con software** porque, si algo me quedaba claro es que **más binario que una app no puede ser. 
Es como un puente real, de los que usamos para cruzar ríos: está y funciona para las personas, o no está.** No hay interpretación, no hay una _historia que contar_, 
tenía que entregar un sitio web que sirviera y ya.  
Acepté, agarré mis cosas y dije:
<img src="/hustle_mode.jpg" alt="imagen con leyenda hustle mode on" width="200" class="center"/>

# Crónica de una muerte anunciada
El banco en cuestión había cambiado de director 3 veces en 3 años, con ello, también hubo cambios de personal, estructura, todo. 
Eso era preocupante, pero no tenía por qué detenernos. Al final del día, **nosotros éramos nuestra propia área, independiente y con una meta clara y tangible**
(al menos en términos virtuales). Éramos un equipo nuevo, motivado, y mixto, 50% con años de experiencia en software, 50% con años de experiencia en el negocio 
particular del banco.
Básicamente, una fusión entre el área de crédito (100% negocio), y el área de tecnología (100% ingeniería de software).   
**Hambre, equipo, y apoyo organizacional, no había más que pudiéramos pedir.**
<br></br>
**¿Y ahora?**   
Es fácil adivinar que mi rol tenía requerimientos más _senior_ que la experiencia que yo tenía al momento de asumirlo.  
Cuando te dicen quiero un API en python, pues vas y construyes un, pero **cómo respondes a la pregunta ¿y por qué python?** ¿Qué 
pasa si te digo que nosotros usamos java con tomcat?
Ok, entonces python, las requests van con puro REST, ¿cierto? ¿Con graphql? La verdad no lo usamos. ¿Múltiples repos? Solemos hacerlo solo en 1, y pues puro java.
Por cierto, ¿en qué montamos el front? React, Vue, o Angular. Ok. Angular*JS*, ¿verdad?  
Vale, sí, react es flexible, create-react-app. Ah, pero CRA ya no se usa, ¿o sí? ¿No? ¿Cómo? ¿Pues qué hace Next o qué?
No, no tenemos nube, pero aquí está un server con postgres. ¿Y por qué quieres que el server tenga internet?  
**En resumen, preguntas y barreras organizacionales por todos lados.**
<br></br>
En mi mejor esfuerzo, **consumí toda la información posible**:  
**-** Videos de [Theo Browne](https://twitter.com/t3dotgg), el único ingeniero senior que encontré con contenido de conceptos arquitectónicos.  
**-**  [Fundamentals of sofware architecture](https://www.oreilly.com/library/view/fundamentals-of-software/9781492043447/), 
[Designing data-intensive applications](https://www.oreilly.com/library/view/designing-data-intensive-applications/9781491903063/), porque Theo no me iba a enseñar todo.  
**-** [Inspired](https://www.svpg.com/books/inspired-how-to-create-tech-products-customers-love-2nd-edition/), 
[Build](https://www.goodreads.com/book/show/59696349-build), de lo contrario, cómo sabría que a la gente le iba a gustar la app.  
**-** [Empowered](https://www.svpg.com/books/empowered-ordinary-people-extraordinary-products/), [Leaders eat last](https://simonsinek.com/books/leaders-eat-last/),
porque no iba a repetir los errores de mis managers pasados.  
**-** [Sprint](https://www.thesprintbook.com/), porque _agile_<sup class="tm">TM</sup>  
**Y fallé.** Pero, curiosamente, **no por las diferencias de mi experiencia con el rol que asumí.**
<br></br>
**La app sí vio la luz**.  
Tenía sus bugs, como toda app, para eso había un backlog, pero cumplía con su propósito de realizar un abordaje de clientes
y llevarlos por un proceso definido de negocio.
**Lo importante es que funcionaba, ahí estaba, tenía dominio web público, seguridad en lo posible, una arquitectura definida, front, back, tenía todo lo que estaba en alcance**. 
Se había hecho todo bien en términos técnicos, por supuesto, gracias a grandes profesionistas (si están leyendo esto, sepan que les agradezco mucho).
También se había hecho lo mejor posible en términos de negocio, recordar que era un equipo mixto y, al final del día, diseñamos el sistema juntos.  
He ahí un puente, un puente de madera, pero funcional. Y nadie lo cruzó...  
**¿Qué falló? ¿Por qué no agregó valor?**
<br></br>
La organización cambió de director, y **la nueva dirección francamente no tuvo interés en un producto digital**. 
Nos mataron silenciosamente, pasaron algunos meses de sentirme inútil, y renuncié.
No fue inmediato, en particular porque la frustración fue grande, pero terminé racionalizando la experiencia:  
**__El valor agregado está, en todo momento, en el servicio que podemos brindarles a otros. 
No importa el número total de personas, e, inclusive, no importa si es uno mismo.__**

# Girasoles y puentes
**Königsberg** era una ciudad de Prusia, hoy la conocemos como Kaliningrad, Rusia. 
En esta ciudad, en el siglo XVIII se encontraban situados **7 puentes**, que conectaban con sus islas centrales entre sí y con la tierra
que las rodeaba.
La figura de alcalde de esa época solicitó a Leonhard Euler que resolviera la siguiente pregunta: 
**¿Es posible caminar por la ciudad pasando una sola vez por cada puente y regresar al mismo punto de inicio?** 
<img src="/konigsberg_bridges.png" alt="imagen de los puentes de Konigsberg" width="500" class="center"/>

**Euler**, se dice, **consideró trivial el problema**, y se negó a resolverlo, dado que _"el problema no guardaba 
relación alguna con las matemáticas"_<sup>[1](https://99percentinvisible.org/article/the-seven-bridge-problem-how-an-urban-puzzle-inspired-a-new-field-of-mathematics/)</sup>.
Sin embargo, tal parece que el problema nunca salió de su mente, y terminó publicando un escrito en 1741 con una respuesta puntual y 
las abstracciones matemáticas usadas para resolverlo.  
**Ese fue el nacimiento de lo que hoy conocemos como teoría de grafos.** 
<img src="/the_red_vineyard.jpg" alt="imagen de la pintura el viñedo rojo de Van Gogh" width="500" class="center"/>

Es de dominio común que **Vincent Van Gogh** vendió una sola pintura en toda su vida: [El viñedo rojo](https://en.wikipedia.org/wiki/The_Red_Vineyard). 
Si bien, puede no ser cierto<sup>[2](https://www.vangoghmuseum.nl/en/art-and-stories/vincent-van-gogh-faq/how-many-paintings-did-vincent-sell-during-his-lifetime)</sup>,
podemos estar seguros que **no fue reconocido hasta 
sus últimos años de vida**<sup>[3](https://www.vangoghmuseum.nl/en/art-and-stories/vincent-van-gogh-faq/how-did-van-gogh-become-famous-after-his-death)</sup>.  
Aquí es mejor dejar que un gran video demuestre qué pasaría si Van Gogh pudiera saber qué fue de sus obras:
<iframe width="560" height="315" src="https://www.youtube.com/embed/ubTJI_UphPk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

La moraleja es: **la utilidad inmediata no es tan fácil de ver**.  
**Como analista**, bastaba con entregar esa ppt con el análisis _ad hoc_ que explícitamente solicitaba la directora
de la oficina; **como ingeniero de datos**, debió basta con saber que alguien estaba atento a cada tabla, y, también, con el testigo de Airflow dándome su Vo.Bo. de 
jobs finalizados exitosamente; **como ingeniero de software**, debió ser suficiente con saber que mi equipo y yo estábamos contentos con una aplicación web bien hecha.   
Siendo honesto, **no creo que la ppt, mi código de Airflow, o un sitio web de banca algún día se vuelvan teoría de grafos, o El Viñedo Rojo, pero solo me queda 
saber que alguna vez alguien, al menos una parte de mí en el pasado, les dio importancia. Y, claro, también debo tener fe puedo equivocarme y tal 
vez trasciendan más de lo que yo puedo o podré alcanzar a ver.**

# Epílogo
Un gran amigo usa la palabra **charlatán** para describir **aquellas personas cuyo único interés es engañar a los demás para obtener un beneficio**, 
mi pequeña cruzada aquí será combatir esto, armado únicamente de anécdotas reales sobre la vida de trabajo (y, a veces, personal) de un profesionista dedicado a software (estándar y de datos).  
**El hilo conductor de cada publicación será ese, a veces hablando de herramientas de software, a veces 
hablando sobre actividades administrativas, pero siempre tratando de evitar la charlatanería.**  
Como todo en la vida, seguro este blog evolucionará ese objetivo algún día, pero habrá que disfrutar el viaje y valor que genere mientras dure.  
Gracias por leer, y, citando sabias palabras de un gran artista: a empezar el 2023 bien cabrón.


<style>
h1 {
    font-weight: bold;
    font-size: 23px;
    margin-top: 1rem;
    margin-bottom: 0.5rem
}

p > a {
    color:hotpink
}

sup {
    color:hotpink
}

iframe {
  display: block;
  margin-left: auto;
  margin-right: auto;
  margin-top: 0.5rem;
  margin-bottom: 1rem
}

.tm {
    color:black
}

.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  margin-top: 0.5rem;
  margin-bottom: 1rem
}

</style>















