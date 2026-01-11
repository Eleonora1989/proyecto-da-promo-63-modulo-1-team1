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

**Características principales:**
- **Sistema de Desafío:** Mecánica de victoria por acumulación de aciertos y derrota por exceso de fallos.
- **Aleatoriedad:** Las preguntas se desordenan en cada partida gracias a la librería `random`, garantizando que cada experiencia sea única.
- **Interfaz Visual:** Uso de iconos (🎲, ✅, ❌, 🏆, 💀) para una respuesta visual clara y motivadora.
- **Contenido:** Base de datos con 30 preguntas que cubren áreas como Geografía, Ciencia, Arte e Historia.

#### 2.2. Cómo jugar
1. Abrir el notebook `trivial.ipynb` y ejecutar la celda de la función `jugar_trivial()`.
2. Leer la pregunta y las cuatro opciones (**A, B, C o D**) que aparecen en pantalla.
3. Escribir la letra correspondiente y pulsar "Enter".
4. El juego continúa hasta alcanzar uno de los límites de estado o terminar las preguntas.

**Reglas adicionales:**
- **Condición de Victoria:** Debes lograr **5 aciertos** para ganar la partida.
- **Condición de Derrota:** Si cometes **3 fallos**, el juego termina inmediatamente (Game Over).
- **Control manual:** Puedes detener el juego en cualquier momento escribiendo la palabra **"STOP"**.
- **Flexibilidad:** El programa procesa automáticamente la entrada para aceptar tanto mayúsculas como minúsculas.

#### 2.3. Detalles técnicos y funciones principales
- **`jugar_trivial()`**: Función maestra que gestiona el bucle de juego.
  - **Control de flujo:** Utiliza un bucle `while` que evalúa simultáneamente tres condiciones: aciertos, fallos y disponibilidad de preguntas.
  - **Gestión de datos:** Emplea `random.shuffle()` para desordenar la lista de diccionarios que contiene la batería de preguntas.
- **Estructura de Datos:** Uso de una **lista de diccionarios**. Cada diccionario almacena la `pregunta`, la lista de `opciones` y la `respuesta` correcta.
- **Variables de estado:**
  - `acertadas`: Contador de respuestas correctas.
  - `fallos`: Contador de respuestas erróneas.
  - `i`: Índice de posición para recorrer la lista de preguntas.

#### 2.4. Posibles mejoras futuras
- **Mayor batería de preguntas:** Ampliar el repositorio de preguntas para evitar repeticiones.
- **Temáticas seleccionables:** Opción de elegir la temática al inicio: Geografía, Capitales, Historia, Deporte, etc.
- **Temporizador:** Añadir un límite de tiempo por respuesta para aumentar la dificultad.



# 3. Piedra, Papel o Tijera (`piedra_papel_tijera.ipynb`)


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
