# Proyecto Mini Classic Games: EducaPlay

**Mini Classic Games** es una colección de tres juegos clásicos desarrollados en formato **Jupyter Notebook (.ipynb)** por el equipo **Wobers**. Este proyecto busca ofrecer una experiencia de entretenimiento sencilla, dinámica e interactiva para usuarios a partir de 14 años.

## 🚀 Sobre el Proyecto
- **Formato:** Entrega de 3 cuadernos interactivos independientes para facilitar la ejecución y visualización del código.
- **Metodología:** Desarrollo bajo el marco de trabajo **Scrum** por el equipo **Wobers** (6 desarrolladoras), asegurando un producto funcional, testeado y documentado.
- **Tecnología:** Python 3, optimizado para su ejecución en entornos de desarrollo interactivos como Jupyter Notebook y VS Code..

---

## 🎮 Catálogo de Juegos

# 1. El Juego del Ahorcado (`juego-ahorcado-pro.ipynb`)

### 1.1. Descripción general
El **Juego del Ahorcado** es un clásico juego de adivinanza de palabras. El jugador debe descubrir la palabra secreta letra por letra antes de quedarse sin intentos.

Características principales:
- El juego se desarrolla y juega en Python y en español.
- La base de datos cuenta con 300 palabras distribuidas en una lista que incluye las siguientes categorías: ROPA, TECNOLOGIA, ANIMALES, COMIDA, CIUDADES, DEPORTES, COLEGIO/UNIVERSIDAD, HOGAR, PROFESIONES, VIAJES, NATURALEZA, EMOCIONES, OCIO Y TIEMPO.
- Hay 6 intentos por partida, con representación visual del “ahorcado” en cada error iniciando el error con la cabeza del "ahorcado"
- Retroalimentación dinámica y mensajes motivadores y divertidos durante el juego.
- Interfaz por consola simple e intuitiva.

Este enfoque permite que cualquier usuario disfrute del juego sin necesidad de conocimientos de programación.

### 1.2. Cómo jugar
1. Ejecutar el archivo Python que contiene el juego.
2. Introducir **una letra** por turno.
3. El juego indicará si la letra está en la palabra y actualizará la palabra mostrada.
4. La partida termina cuando:
   - Se adivina la palabra (victoria).
   - Se acaban los 6 intentos (derrota).

**Reglas adicionales:**
- No importa si el usuario escribe mayúsculas o vocales con tilde; el programa las convierte automáticamente a minúsculas y simples respectivamente.
- Las letras repetidas se notifican, pero no restan intentos.
- La palabra se muestra con guiones bajos para representar las letras no descubiertas.
- **Nota:** en Jupyter Notebook, después de 3 intentos puede aparecer el mensaje "Output is truncated..."; en ese caso, ajustar la celda a "scrollable" para seguir visualizando la partida completa.

### 1.3. Detalles técnicos y funciones principales
- **`juego_ahorcado()`**: función principal que controla todo el juego.
  - Inicializa la palabra secreta de forma aleatoria.
  - Configura variables: `intentos` (6 por partida), `letras_adivinadas`, `palabra_mostrada`.
  - Contiene el bucle principal donde se gestionan entradas de usuario, actualización de la palabra y del estado del ahorcado.
  - Evalúa condiciones de victoria y derrota, mostrando mensajes adecuados.
  - Cada intento incorrecto va mostrando progresivamente el ahorcado.
- **Variables importantes:**
  - `palabra_secreta` → palabra elegida aleatoriamente de la lista de 300 palabras para la partida.
  - `letras_adivinadas` → lista que almacena las letras introducidas por el jugador.
  - `intentos` → número de oportunidades restantes (inicialmente 6).
  - `palabra_mostrada` → visualización de la palabra con letras descubiertas y guiones bajos.
- **Funciones internas y lógica del juego:**
  - Comprobación de la letra ingresada: si es válida, si ya fue usada, si está en la palabra.
  - Actualización de `palabra_mostrada` con las letras correctas.
  - Gestión de los intentos y dibujo progresivo del ahorcado.
  - Feedback al jugador mediante mensajes dinámicos según el progreso.

Esta estructura modular permite mantener y ampliar fácilmente el juego, así como integrarlo en un proyecto con varios juegos.

### 1.4. Posibles mejoras futuras
- Implementar interfaz gráfica y añadir más elementos gráficos atractivos por el usuario como el uso de emoticonos.



# 2. El Juego del Trivial (`juego-ahorcado-pro.ipynb`)

#### 2.1. Descripción general del juego
El **Trivial** es un juego de preguntas de selección múltiple sobre cultura general. Esta versión destaca por su dinamismo y por incluir un sistema de puntuación que castiga el error, haciendo la experiencia más competitiva.

Características principales:
- El juego se desarrolla y juega en Python y en español.
- La base de datos cuenta con unas 30 preguntas sobre la temáticas de historia, geografía, arte y ciencia distribuidas en una lista.
- Cada pregunta tiene cuatro opciones: A,B,C o D.
- Las preguntas se desordenan en cada partida gracias a la librería `random`, garantizando que cada experiencia sea única.
- Si el jugador acierta 5 partidas, gana. Si el jugador falla 3, pierde.
- Retroalimentación dinámica y interfaz simple e intuitiva: uso de iconos para una respuesta visual y motivadora.

Este enfoque permite que cualquier usuario disfrute del juego sin necesidad de conocimientos de programación.

#### 2.2. Cómo jugar
1. Ejecutar el archivo Python que contiene el juego.
2. Leer la pregunta y las cuatro opciones (**A, B, C o D**) que aparecen en pantalla.
3. Escribir la letra correspondiente y pulsar "Enter".
4. El juego continúa hasta alcanzar uno de los límites de estado o terminar las preguntas.

**Reglas adicionales:**
- No importa si el usuario escribe la letra en mayúscula; el programa la convierte automáticamente a minúsculas.
- Si el usuario no escribe **A, B, C o D**, la respuesta se dará por incorrecta.
- **Condición de Victoria:** Debes lograr **5 aciertos** para ganar la partida.
- **Condición de Derrota:** Si cometes **3 fallos**, el juego termina inmediatamente (Game Over).
- **Control manual:** Puedes detener el juego en cualquier momento escribiendo la palabra **"STOP"**.
- **Nota:** en Jupyter Notebook, después de 3 intentos puede aparecer el mensaje "Output is truncated..."; en ese caso, ajustar la celda a "scrollable" para seguir visualizando la partida completa.

#### 2.3. Detalles técnicos y funciones principales
- **`jugar_trivial()`**: Función maestra que gestiona el bucle de juego.
  - **Control de flujo:** Utiliza un bucle `while` que evalúa simultáneamente tres condiciones: aciertos, fallos y disponibilidad de preguntas.
  - **Gestión de datos:** Emplea `random.shuffle()` para desordenar la lista de diccionarios que contiene la batería de preguntas y no las repite en la misma partida.
- **Estructura de Datos:** Uso de una **lista de diccionarios**. Cada diccionario almacena la `pregunta`, la lista de `opciones` y la `respuesta` correcta.
- **Variables de estado:**
  - `acertadas`: Contador de respuestas correctas.
  - `fallos`: Contador de respuestas erróneas.
  - `i`: Índice de posición para recorrer la lista de preguntas.

#### 2.4. Posibles mejoras futuras
- Ampliar el repositorio de preguntas.
- Opción de elegir la temática al inicio: Geografía, Capitales, Historia, Deporte, etc.



# 3. Piedra, Papel o Tijera (`piedra_papel_tijera.ipynb`)

#### 3.1. Descripción general del juego
**Piedra, papel o tijera** es un juego de enfrentamiento entre dos jugadores quienes deben elegir entre piedra, papel o tijera. La lógica de victoria sigue el patrón clásico: "papel" gana a "piedra", "piedra" gana a "tijera" y "tijera" gana a "papel".

Esta versión ha sido diseñada para que dos jugadores compitan simultáneamente en local, e incluye un sistema de puntuación que castiga el error en la escritura, haciendo la experiencia mucho más competitiva y exigente.

Características principales:
- El juego se desarrolla y juega en Python y en español.
- Permite la competición directa entre dos personas en el mismo dispositivo.
- Partidas rápidas al mejor de 3 (el primero que llega a 3 puntos gana).
- El programa es capaz de procesar el texto eliminando espacios accidentales y omitiendo la diferencia entre mayúsculas y minúsculas siempre que introduzca una de las opciones predeterminadas "piedra", "papel" o "tijera".
- El juego tiene un albitraje estricto: si un jugador introduce una opción no válida, el punto se asigna automáticamente al oponente.
- Retroalimentación dinámica y interfaz simple e intuitiva: uso de iconos para una respuesta visual y motivadora.

Este enfoque permite que cualquier usuario disfrute del juego sin necesidad de conocimientos de programación.

#### 3.2. Cómo jugar

1. Ejecutar el archivo Python que contiene el juego.
2. El **Jugador 1** elige su opción.
3. El **Jugador 2** elige su opción a continuación.
4. El programa muestra el ganador de la ronda y el marcador actualizado.
5. El juego finaliza cuando alguien alcanza los 3 puntos.
   
**Reglas adicionales:**
- Si un jugador falla o introduce una respuesta que no esté contemplada: el punto se lo lleva el otro jugador.
- **Nota:** en Jupyter Notebook, después de 3 intentos puede aparecer el mensaje "Output is truncated..."; en ese caso, ajustar la celda a "scrollable" para seguir visualizando la partida completa.

#### 3.3. Detalles técnicos y funciones principales
- **`decidir_ganador(jugador1, jugador2)`**: Función que encapsula la lógica de comparación de elementos para determinar el ganador de la ronda.
- **`jugar()`**: Motor del juego que controla el bucle principal y el marcador.
- **Validación de Entradas Cruzada**: El código utiliza variables booleanas (`valido1`, `valido2`) para verificar las respuestas contra la lista de `opciones` permitidas antes de calcular el resultado.
- **Control de flujo avanzado**: 
  - Uso de `continue` para reiniciar la ronda en caso de entradas inválidas sin interrumpir el flujo.
  - Uso de `break` para finalizar la partida cuando se cumple la condición de victoria (3 puntos).

#### 3.4. Posibles mejoras futuras
- Personalizar más el juego con la opción de introducir el nombre de cada jugador

# 🛠️ Instrucciones de ejecución
Para asegurar una correcta visualización de los juegos por parte del cliente:
1. Abrir el archivo `.ipynb` correspondiente en un entorno compatible (Jupyter, VS Code o Google Colab).
2. Ejecutar la celda de código principal.
3. Interactuar a través de la consola que aparecerá bajo la celda.


# 👥 Equipo Wobers
Proyecto desarrollado por un equipo de 6 programadoras junior comprometidas con la calidad del código y la metodología ágil:
- **Scrum Master:** Coordinación de sprints y flujo de trabajo.
- **Documentarista:** Responsable de la claridad y estructura de la presente documentación técnica.
- **Desarrolladoras:** Implementación de la lógica y validación de los juegos
