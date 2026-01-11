# Proyecto Mini Classic Games: EducaPlay

**Mini Classic Games** es una colección de tres juegos clásicos desarrollados en formato **Jupyter Notebook (.ipynb)** por el equipo **Wobers**. Este proyecto busca ofrecer una experiencia de entretenimiento sencilla, dinámica e interactiva para usuarios a partir de 14 años.

## 🚀 Sobre el Proyecto
- **Formato:** Entrega de 3 cuadernos interactivos independientes para facilitar la ejecución y visualización del código.
- **Metodología:** Desarrollo bajo el marco de trabajo **Scrum** por el equipo **Wobers** (6 desarrolladoras), asegurando un producto funcional, testeado y documentado.
- **Tecnología:** Python 3, optimizado para su ejecución en entornos de desarrollo interactivos como Jupyter Notebook y VS Code.

---

## 🎮 Catálogo de Juegos

## 1. El Juego del Ahorcado (`juego-ahorcado-pro.ipynb`)

### 1.1. Descripción general
El **Juego del Ahorcado** es un clásico juego de adivinanza de palabras. El jugador debe descubrir la palabra secreta letra por letra antes de quedarse sin intentos.

**Características principales:**
- El juego se desarrolla y juega en Python y en español.
- La base de datos cuenta con **300 palabras** distribuidas en categorías como: ROPA, TECNOLOGÍA, ANIMALES, COMIDA, CIUDADES, DEPORTES, COLEGIO/UNIVERSIDAD, HOGAR, PROFESIONES, VIAJES, NATURALEZA, EMOCIONES, OCIO Y TIEMPO.
- Hay 6 intentos por partida, con representación visual del “ahorcado” en cada error iniciando con la cabeza del personaje.
- Retroalimentación dinámica y mensajes motivadores durante el juego.

### 1.2. Cómo jugar
1. Ejecutar el archivo que contiene el juego.
2. Introducir **una letra** por turno.
3. El juego indicará si la letra es correcta y actualizará la visualización.
4. La partida termina cuando se adivina la palabra (**victoria**) o se acaban los 6 intentos (**derrota**).

**Reglas adicionales:**
- Conversión automática de mayúsculas y tildes para evitar errores de usuario.
- Las letras repetidas se notifican, pero no restan intentos.
- **Nota:** En Jupyter Notebook, si el output se trunca tras varios intentos, ajustar la celda a "scrollable".

### 1.3. Detalles técnicos y funciones principales
- **`juego_ahorcado()`** -> Función principal que controla el flujo, gestiona el bucle de eventos y evalúa las condiciones de victoria o derrota.
- **Variables importantes:**
  - `palabra_secreta` -> Palabra elegida aleatoriamente de la lista de 300 términos.
  - `letras_adivinadas` -> Lista que almacena las letras introducidas por el jugador.
  - `intentos` -> Número de oportunidades restantes (inicialmente 6).
  - `palabra_mostrada` -> Visualización dinámica de la palabra con letras descubiertas y guiones bajos.
- **Funciones internas y lógica:**
  - Comprobación de la letra: Validación de caracteres válidos y control de uso previo.
  - Renderizado: Gestión de los intentos y dibujo progresivo del ahorcado en ASCII.

### 1.4. Posibles mejoras futuras
- Implementar interfaz gráfica y añadir emoticonos para mayor atractivo visual.

---

## 2. El Juego del Trivial (`trivial.ipynb`)

### 2.1. Descripción general del juego
El **Trivial** es un juego de preguntas de selección múltiple sobre cultura general. Esta versión destaca por su dinamismo y por incluir un sistema de puntuación que castiga el error, haciendo la experiencia más competitiva.

**Características principales:**
- La base de datos cuenta con **30 preguntas** sobre temáticas de historia, geografía, arte y ciencia.
- Cada pregunta ofrece cuatro opciones: A, B, C o D.
- Aleatoriedad: Las preguntas se desordenan en cada partida mediante la librería `random`.
- **Condiciones de fin:** El jugador gana al alcanzar 5 aciertos y pierde al acumular 3 fallos.
- Retroalimentación dinámica mediante el uso de iconos para una respuesta visual inmediata.

### 2.2. Cómo jugar
1. Ejecutar el archivo que contiene el juego.
2. Leer la pregunta y las opciones (**A, B, C o D**) en pantalla.
3. Escribir la letra de la respuesta y pulsar "Enter".
4. El juego continúa hasta alcanzar la victoria o la derrota.

**Reglas adicionales:**
- Las entradas se normalizan automáticamente a mayúsculas.
- Si el usuario introduce una opción distinta a A, B, C o D, la respuesta se cuenta como incorrecta.
- **Control manual:** Se puede detener el juego en cualquier momento escribiendo la palabra **"STOP"**.

### 2.3. Detalles técnicos y funciones principales
- **`jugar_trivial()`** -> Función maestra que gestiona el bucle `while` y las tres condiciones de salida simultáneas.
- **Estructura de Datos** -> Uso de una **lista de diccionarios** donde cada objeto contiene la pregunta, la lista de opciones y la respuesta correcta.
- **Variables de estado:**
  - `acertadas` -> Contador de respuestas correctas (objetivo: 5).
  - `fallos` -> Contador de respuestas erróneas (límite: 3).
  - `i` -> Índice de posición para recorrer la lista de preguntas sin repeticiones.

### 2.4. Posibles mejoras futuras
- Ampliar el repositorio de preguntas y añadir selección de temática inicial (Deporte, Historia, etc.).

---

## 3. Piedra, Papel o Tijera (`piedra_papel_tijera.ipynb`)

### 3.1. Descripción general del juego
**Piedra, papel o tijera** es un juego de enfrentamiento entre dos jugadores. La lógica de victoria sigue el patrón clásico: el "papel" gana a la "piedra", la "piedra" gana a la "tijera" y la "tijera" gana al "papel".

Esta versión permite que dos jugadores compitan simultáneamente en local e incluye un sistema de puntuación que castiga el error en la escritura, haciendo la experiencia más exigente y competitiva.

**Características principales:**
- **Modo 1vs1:** Competición directa entre dos personas en el mismo dispositivo.
- **Meta de puntuación:** Partidas rápidas al mejor de 3 puntos.
- **Arbitraje estricto:** Si un jugador introduce una opción no válida, el punto se asigna automáticamente al oponente.
- **Resiliencia:** El programa procesa el texto eliminando espacios y diferenciación entre mayúsculas y minúsculas.

### 3.2. Cómo jugar
1. Ejecutar el archivo que contiene el juego.
2. El **Jugador 1** y el **Jugador 2** introducen sus elecciones por turnos.
3. El programa muestra el resultado de la ronda y el marcador.
4. El juego finaliza cuando alguien alcanza los **3 puntos**.

**Reglas adicionales:**
- Si ambos jugadores fallan el input simultáneamente, la ronda se declara nula y nadie suma puntos.
- Si solo uno introduce una opción inválida, el punto es para el rival.

### 3.3. Detalles técnicos y funciones principales
- **`decidir_ganador(jugador1, jugador2)`** -> Función lógica que aplica las reglas de comparación para determinar el ganador de cada ronda.
- **`jugar()`** -> Motor del juego que controla el bucle principal y la actualización del marcador.
- **Lógica de Validación:**
  - `valido1` / `valido2` -> Variables booleanas que verifican las respuestas contra la lista de opciones permitidas.
  - `continue` -> Permite reiniciar la ronda inmediatamente en caso de entradas inválidas sin romper el flujo.
  - `break` -> Finaliza la partida limpiamente al alcanzar la condición de victoria.

### 3.4. Posibles mejoras futuras
- Personalizar la experiencia permitiendo introducir nombres personalizados para cada jugador y añadir un modo contra la IA.

---

## 🛠️ Instrucciones de ejecución
Para asegurar una correcta visualización de los juegos por parte del cliente:
1. Abrir el archivo `.ipynb` correspondiente en un entorno compatible (**Jupyter**, **VS Code** o **Google Colab**).
2. Ejecutar la celda de código principal.
3. Interactuar a través de la consola interactiva que aparecerá bajo la celda.

---

## 👥 Equipo Wobers
Proyecto desarrollado por un equipo de 6 programadoras junior bajo metodología ágil:
- **Scrum Master:** Coordinación de sprints y flujo de trabajo.
- **Documentarista:** Responsable de la claridad y consistencia de la documentación técnica.
- **Desarrolladoras:** Implementación de la lógica, validación y control de errores.
