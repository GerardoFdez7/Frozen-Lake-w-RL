# Frozen Lake con Q-Learning y Gymnasium

Este proyecto implementa un agente de aprendizaje por refuerzo (Reinforcement Learning) utilizando el algoritmo clásico de **Q-Learning** para resolver el entorno **FrozenLake-v1** provisto por la librería estándar de la industria `gymnasium`.

## Descripción del Proyecto

El entorno de Frozen Lake consiste en una cuadrícula (mapa de 4x4) en donde el agente debe navegar desde un punto de inicio hasta una meta sin caer en los agujeros en el hielo. En esta implementación, el entorno se ha configurado de forma estocástica (`is_slippery=True`), lo que significa que el hielo es resbaladizo, por lo que las acciones que escoge el agente no siempre resultan en el movimiento deseado. Esto añade un mayor nivel de desafío al entrenamiento.

Todo el código fuente y las visualizaciones se encuentran desarrolladas en el Noteook principal: `frozen_lake_w_rl.ipynb`.

## Tareas Implementadas

El notebook está estructurado de manera progresiva en tres grandes bloques:

1. **Task 2.1 - Inicialización y Exploración**:
   - Configuración inicial del entorno de Gymnasium (`FrozenLake-v1`, mapa `4x4`, modo de render `rgb_array`).
   - Exploración y análisis del espacio de estados (16 estados discretos) y del espacio de acciones (4 acciones posibles: izquierda, abajo, derecha, arriba).

2. **Task 2.2 - Algoritmo Q-Learning**:
   - Implementación desde cero del entrenamiento usando **Q-Learning**.
   - Se utiliza una política **Epsilon-Greedy** para equilibrar la exploración del mapa al inicio y la explotación del conocimiento adquirido conforme el entrenamiento progresa.
   - Se emplea un decrecimiento (decay) gradual del nivel de exploración (epsilon $\epsilon$) para un total de 10,000 episodios simulados.
   - Como resultado, se calcula y se imprime la matriz o Tabla Q final con los valores de las acciones para cada estado.

3. **Task 2.3 - Prueba y Evaluación**:
   - Evaluación del comportamiento puramente "codicioso" (explotación total, $\epsilon=0$) a lo largo de 10 episodios de prueba.
   - Recopilación de métricas sobre la política aprendida mediante el cálculo del _Win Rate_ (% de triunfos).
   - Animación visual de uno de los recorridos del agente hacia la meta exitosamente, haciendo uso de `matplotlib` e `IPython.display`.

## Tecnologías Utilizadas / Dependencias

Para la ejecución correcta del notebook, son necesarias las siguientes librerías de Python:

- `gymnasium` (y `pygame` para el render)
- `numpy`
- `matplotlib`
- `ipython` (proporcionado junto al entorno de ejecución típico de los notebooks)

Puedes instalar estas dependencias (se incluye un comando `%pip install` en la primera celda del código) vía:

```bash
pip install gymnasium pygame numpy matplotlib ipython
```

## Ejecución

1. Clona el repositorio o descarga el contenido del proyecto.
2. Asegúrate de abrir el directorio en un entorno compatible como **Jupyter Notebook**, **Jupyter Lab** o la extensión de Jupyter de **Visual Studio Code**.
3. Abre el archivo `frozen_lake_w_rl.ipynb`.
4. Ejecuta cada celda secuencialmente para inicializar dependencias, compilar la Tabla Q entrenando al agente y finalizar con la validación visual de la solución encontrada por el agente de Reinforcement Learning.
