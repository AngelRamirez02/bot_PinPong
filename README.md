# bot_PinPong

Componentes principales

PongAgent
La clase PongAgent implementa el algoritmo de Q-Learning para aprender a jugar Pong:

Q-Table: Almacena los valores Q (calidad) para cada combinación de estado-acción.
Exploración vs. Explotación: Utiliza un parámetro ratio_explotacion para balancear entre tomar acciones aleatorias (exploración) y elegir la mejor acción conocida (explotación).
Actualización de políticas: Actualiza los valores Q basándose en las recompensas obtenidas y estados futuros.

PongEnvironment
La clase PongEnvironment simula el entorno del juego Pong:

Estado del juego: Controla la posición de la pelota, el jugador y mantiene la puntuación.
Sistema de recompensas: Otorga +10 puntos por golpear la pelota y -10 por perderla.
Visualización: Permite animar el juego con gráficos matplotlib.

Función play()
Coordina el entrenamiento del agente:

Ejecuta múltiples partidas para entrenar al agente.
Registra estadísticas de rendimiento (puntuación media, pasos, etc.).
Permite visualizar el juego durante el entrenamiento o la evaluación.

Algoritmo Q-Learning

Inicialización: Se crea una tabla Q con valores iniciales de cero.
Selección de acciones: En cada estado, el agente:

Con probabilidad ε: selecciona una acción aleatoria (exploración).
Con probabilidad 1-ε: selecciona la acción con mayor valor Q (explotación).


Actualización de valores Q:

Q(s,a) = Q(s,a) + α [r + γ·max Q(s',a') - Q(s,a)]
Donde:

s, a = estado y acción actuales
s' = estado siguiente
r = recompensa recibida
α = tasa de aprendizaje
γ = factor de descuento





Hiperparámetros clave

discount_factor (γ): Determina la importancia de recompensas futuras (0.2 por defecto).
learning_rate (α): Controla la tasa de actualización de nuevos conocimientos (0.1 por defecto).
ratio_explotacion (1-ε): Balanceo entre explorar nuevas acciones y explotar conocimiento existente (0.85 por defecto).

Visualización
Para visualizar el juego, se debe activar el parámetro animate=True en la función play()
