# Pensamiento-computacional-Examen

## Información del proyecto

**Nombre del proyecto:** Pibble’s Beach Party Dress-Up Game

**Autor:** Maximiliano Tasso

**Curso:** Pensamiento Computacional

**Año:** 2026

**Software utilizado:** p5.js

**Link al proyecto en p5.js:**
https://editor.p5js.org/maximiliano.tasso/full/EmInqtMPI
https://editor.p5js.org/maximiliano.tasso/sketches/EmInqtMPI

---

## Descripción general

*Pibble’s Beach Party* es un sistema visual interactivo desarrollado en p5.js que funciona como un pequeño juego de vestir inspirado en los dress-up games de los 2000. El usuario prepara a Pibble para una fiesta de verano en la playa, seleccionando distintos gorros, tops y bottoms. Luego, al presionar el botón **Take a Pic**, el sistema genera una beach card final personalizada según la combinación de gorro y top elegida.

El proyecto utiliza imágenes, sonidos, estados, eventos, inputs y outputs visuales para construir una experiencia interactiva con una estética playera, lúdica y nostálgica.

---

## Descripción objetiva

El proyecto se divide en tres pantallas principales:

1. **Pantalla de inicio**
   Se muestra una imagen introductoria (`intro.png`) junto a un botón de Play (`play.png`). Al hacer click sobre el botón, el sistema avanza hacia la pantalla de vestir y comienza a sonar la música principal.

2. **Pantalla de vestir**
   Se muestra una imagen base (`base.png`) con Pibble y las prendas disponibles. El usuario puede hacer click sobre distintas zonas de la pantalla para seleccionar gorros, tops y bottoms. Cada prenda seleccionada aparece como una capa visual sobre Pibble.

3. **Pantalla final / Beach Card**
   Al presionar el botón `take.png`, el sistema pasa a una tarjeta final. Esta tarjeta cambia dependiendo de la combinación de gorro y top seleccionada. Por ejemplo, si el usuario elige el gorro A y el top X, el sistema muestra la imagen `AX.png`.

Además, en la pantalla final el usuario puede presionar la tecla **S** para generar stickers aleatorios. Al mover el mouse, el tamaño de estos stickers cambia dinámicamente.

---

## Descripción conceptual

El mayor referente que tome fue el juego Polly's Rockstar Makeover, este juego representaba bastante bien la estetica y funcionalidad que buscaba representar, este juego tiene tres estados distintivos, tiene un layout de ropa y peinados para emparejar y hace uso de imágenes y sonido. 
En estetica tome referencias de las interfaces infantiles de los 2000 como los juegos flash o cd-rom, estos juegos normalmente ocupan botones simples y claros que indican lo que hay que hacer para una audiencia infantil. Otro aspecto que tome de estos juegos, es el uso de capas para crear overlays, los outfits iban por sobre una foto base.

---

## Referentes visuales

Los referentes principales del proyecto son:

* Juegos de vestir web de los 2000.
* Interfaces infantiles y lúdicas de navegador.
* Estética "Y2K".
* Stickers digitales, postales y tarjetas playeras.
* Gráficas de verano.

### Imágenes de referencia

![Referencia 1](/imagenes/referencias.png)

---

## Sistema computacional

El sistema está organizado a partir de una variable principal llamada `estado`, que controla qué pantalla se muestra en cada momento.

### Estados del sistema

**Estado 0: Pantalla de inicio**
Muestra `intro.png` y el botón `play.png`.

**Estado 1: Pantalla de vestir**
Muestra `base.png`, las prendas disponible y seleccionadas y el botón `take.png`.

**Estado 2: Pantalla final / Beach Card**
Muestra una tarjeta final según la combinación de gorro y top. También permite generar stickers con la tecla S.

---

## Inputs

El sistema recibe distintos inputs del usuario:

* Click sobre el botón **Play**.
* Click sobre las prendas de ropa.
* Click sobre el botón **Take a Pic**.
* Presionar la tecla **S**.
* Movimiento horizontal del mouse.

---

## Procesos

El sistema procesa los inputs de distintas maneras:

* Detecta clicks dentro de zonas específicas mediante la función `insideBox()`.
* Cambia el valor de `estado` para pasar entre pantallas.
* Guarda las prendas seleccionadas en variables como `hatActual`, `topActual` y `bottomActual`.
* Guarda códigos de selección en `hatCode` y `topCode`.
* Une los códigos de gorro y top para generar combinaciones como `AX`, `BY` o `CZ`.
* Usa esa combinación para elegir qué imagen final mostrar.
* Usa `random()` para generar posiciones y tipos de stickers.
* Usa `map()` para transformar la posición del mouse en el tamaño de los stickers.

---

## Outputs

El sistema genera distintos outputs visuales y sonoros:

* Cambio de pantalla entre inicio, vestir y beach card.
* Aparición de prendas sobre Pibble.
* Reproducción de sonido al hacer click.
* Música durante la pantalla de vestir.
* Cambio de sonido al llegar a la beach card.
* Imagen final personalizada según la combinación elegida.
* Stickers aleatorios en la pantalla final.
* Cambio de tamaño de stickers según el movimiento del mouse.

---

## Eventos y transiciones

| Evento               | Resultado                                             |
| -------------------- | ----------------------------------------------------- |
| Click en Play        | Cambia del estado 0 al estado 1                       |
| Click en una prenda  | La prenda aparece sobre Pibble                        |
| Click en Take a Pic  | Cambia del estado 1 al estado 2                       |
| Click en Take a Pic  | Detiene la música principal y reproduce `coconut.mp3` |
| Tecla S              | Genera stickers aleatorios                            |
| Movimiento del mouse | Cambia el tamaño de los stickers                      |

---

## Recursos multimedia utilizados

[Archivos empaquetados](/imagenes/Recursos.zip)

### Sonidos

* `click.mp3`: sonido de retroalimentación al hacer click.
* `ilikeyourlook.mp3`: música que suena durante la pantalla de vestir.
* `coconut.mp3`: sonido o música que se reproduce al llegar a la beach card final.

Los recursos multimedia no funcionan solo como decoración, tambien ayudan a construir la lógica del sistema. Las imágenes permiten vestir al personaje y generar resultados visuales personalizados, mientras que los sonidos marcan acciones y cambios de estado.

---

## Explicación de la interacción

La experiencia comienza en una pantalla de inicio. El usuario presiona el botón **Play**, lo que cambia el sistema al estado de vestir y activa la música principal.

En la pantalla de vestir, el usuario hace click sobre distintas prendas. Cada click selecciona una imagen y la guarda en una variable. Luego esa imagen se dibuja encima de la base, funcionando como una capa visual sobre Pibble.

Cuando el usuario presiona **Take a Pic**, el sistema detiene la música del dress-up, reproduce un nuevo sonido y cambia a la pantalla final. En esta última pantalla, se muestra una beach card que depende de la combinación de gorro y top elegida.

Además, si el usuario presiona la tecla **S**, se generan stickers aleatorios sobre la tarjeta. Estos stickers cambian de tamaño según la posición horizontal del mouse.

---

## Uso de `random()`

El proyecto utiliza `random()` para generar stickers en posiciones aleatorias dentro de la beach card final. También se usa para definir si cada sticker será una estrella o una flor.

Esto permite que la pantalla final tenga una variación visual distinta cada vez que el usuario presiona la tecla S.

---

## Uso de `map()`

El proyecto utiliza `map()` para transformar la posición horizontal del mouse en el tamaño de los stickers.

Cuando el mouse está más hacia la izquierda, los stickers se ven más pequeños. Cuando el mouse se mueve hacia la derecha, los stickers aumentan de tamaño.

Esto permite que la beach card final siga siendo interactiva incluso después de haber terminado la selección de ropa.

---

## Diagrama de flujo

![Diagrama de flujo](/imagenes/diagrama.png)


---

## Registro visual del proceso

![proceso1](/imagenes/proceso.png)
![proceso2](/imagenes/proceso1.png)
![proceso3](/imagenes/proceso2.png)
![proceso4](/imagenes/proceso3.png)
![proceso5](/imagenes/proceso4.png)
![proceso6](/imagenes/proceso8.png)
![proceso7](/imagenes/proceso7.png)
![proceso8](/imagenes/proceso6.png)
![proceso9](/imagenes/proceso5.png)





### Bocetos iniciales

la idea original era que el sistema fuera hecho con renders 3d originales y el final fuera una animacion en 3d, pero debido a las limitaciones de tiempo tuve que reducir la escala y la complejidad.

![Boceto](/imagenes/boceto.jpeg)
![Boceto2](/imagenes/boceto2.jpeg)
![Boceto3](/imagenes/boceto3.jpeg)
![Boceto4](/imagenes/boceto4.png)

### Desarrollo de interfaz

![Pantalla de inicio](/imagenes/inicio.png)
![Pantalla de vestir](/imagenes/vestir.png)
![Beach card final](/imagenes/final.png)

## Decisiones de diseño

Una de las decisiones principales fue trabajar con un canvas de **500 × 459 px**, ya que todas las imágenes del sistema fueron diseñadas para ese formato. Esto permitió que las prendas funcionaran como capas PNG colocadas directamente sobre la base, sin necesidad de reposicionarlas mediante código, el tamaño de las imagenes tambien ayudo a reducir los tiempos de espers

También se decidió que la beach card final dependiera solamente de la combinación entre gorro y top. Esta decisión simplifica el sistema, reduce la cantidad de imágenes finales necesarias y permite mantener una lógica clara para el usuario y para el código.

El uso de stickers aleatorios en la pantalla final busca reforzar la estética de postal, fiesta y personalización. Estos elementos funcionan como una capa decorativa generada por el sistema y activada por el usuario.

---

## Dificultades encontradas

Durante el desarrollo surgieron algunas dificultades técnicas:

* Definir zonas clickeables para cada prenda.
* Crear una tercera pantalla que no fuera solo decorativa, sino que respondiera a las elecciones del usuario.
* Integrar `random()` y `map()` de una manera coherente con la experiencia.

Una de las soluciones más importantes fue simplificar la lógica de la pantalla final. En lugar de crear una tarjeta para todas las combinaciones posibles de gorro, top y bottom, la imagen final se definió solo a partir de gorro y top.

---

## Aprendizajes

A través de este proyecto aprendí a estructurar un sistema visual interactivo usando estados. También aprendí a trabajar con imágenes como capas, a detectar clicks en zonas específicas, a cargar sonidos, y a generar respuestas visuales dinámicas según las acciones del usuario.

---

## Reflexión final

*Pibble’s Beach Party* es un proyecto que traduce la lógica de los juegos de vestir de los 2000 a un sistema interactivo en p5.js. La experiencia utiliza una estructura simple, pero organizada en tres estados claros: inicio, vestir y resultado final.

El proyecto no busca replicar literalmente un juego antiguo, sino reinterpretar su lógica visual. La selección de prendas, la generación de una beach card y la aparición de stickers permiten que el usuario participe en la creación de una imagen final personalizada.

El mayor desafío fue equilibrar una propuesta visual coherente con una estructura de código que pudiera ser entendida y explicada con claridad. Por eso, se priorizó una lógica simple pero efectiva, basada en estados, condicionales, funciones, imágenes, sonidos y respuestas interactivas.

---

## Créditos/Fuentes

Sonido de click: Shine 11 – BenKirb [https://pixabay.com/sound-effects/film-special-effects-shine-11-268907/]

Sonido de camara: Camera – irinairinafomicheva [https://pixabay.com/sound-effects/technology-camera-13695/]

Musica de juego: I like your look (instrumental) – Kim Petras [https://www.youtube.com/watch?v=byCCcGEU6bY]

Musica del final: Coconut (instrumental) – Smile.dk [https://www.youtube.com/watch?v=TATTKVx5tHY] 

Recursos de ropa creados por gemini.

Los recursos visuales, graficos y 3d fueron creados por el autor.

Todos los derechos de los audios y la música utilizados en este contenido pertenecen a sus respectivos dueños, No reclamo la propiedad de ningún sonido presentado en este sistema.
