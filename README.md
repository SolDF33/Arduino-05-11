# Arduino-05-11
Trabajo para Arquitectura de las Computadoras

## 🚀 Solución de Red Neuronal para Coche Autónomo - [Tu Nombre o ID]

Este proyecto implementa una Red Neuronal Artificial (RNA) entrenada para controlar las acciones (aceleración, giro, alarma) de un coche autónomo en un entorno simulado (Wokwi), basándose en 4 entradas sensoriales.

### 1. Definición del Problema (El Cerebro)

* **Objetivo:** Desarrollar una RNA que mapee 4 entradas a 5 salidas (4 de movimiento + 1 alarma).
* **Arquitectura Final:** 5 Nodos de Entrada (4 sensores + 1 *Bias*) $\rightarrow$ 7 Nodos Ocultos $\rightarrow$ 5 Nodos de Salida (Motores + Alarma).
* **Función de Activación:** Tangente Hiperbólica (`tanh`).
* **Entradas Reales:**
    1.  Cercanía/Distancia al obstáculo.
    2.  Dirección del obstáculo (posición del servo).
    3.  Línea Negra detectada (Nueva).
    4.  Batería Baja (Nueva).
* **Salidas Reales:**
    1.  Motor 1 Avanzar (M1A)
    2.  Motor 1 Retroceder (M1R)
    3.  Motor 2 Avanzar (M2A)
    4.  Motor 2 Retroceder (M2R)
    5.  **ALARMA (Nueva)**.

### 2. Diseño y Generación de Datos (La Tabla de la Verdad)

* **Descripción:** Se diseñó una tabla de verdad con **[Indicar el número total de filas, ej: 16]** filas, cubriendo todas las combinaciones, priorizando la seguridad y la nueva lógica.
* **Lógica Clave de la Alarma (Nueva):**
    * La alarma se activa con un valor de salida de **1.0** si la entrada Línea Negra es **1.0** y/o si la entrada Batería Baja es **1.0**.

### 3. Entrenamiento (Google Colab)

* **Entorno:** Google Colab / Python (TensorFlow, Keras o implementación NumPy).
* **Métricas Clave:** Se logró una precisión de entrenamiento del **[Colocar tu precisión final, ej: 99.8%]** tras **[Colocar el número de épocas/iteraciones]** épocas.
* **Pesos Exportados:** Los pesos finales (`HiddenWeights` y `OutputWeights`) fueron exportados en formato C (float array) para su integración en el Arduino.

### 4. Implementación y Pruebas (Wokwi)

* **Entorno:** Plataforma de simulación Wokwi (Arduino Uno).
* **Integración:** Los 45 pesos resultantes del entrenamiento fueron transferidos y codificados directamente en el archivo `sketch.ino` de Arduino.
* **Evidencia de Funcionamiento:**
    * [Tu URL de Wokwi] **<-- ¡Pega aquí el enlace que guardaste!**
* **Pruebas Exitosas:** Se verificó en el Monitor Serial que la `Salida5 (ALARMA)` se activa con `1`
  
https://colab.research.google.com/drive/1vKgDX4eM2bDklK4d9r7FZgX7Yz7hGDGt?usp=sharing

https://wokwi.com/projects/446825799004604417
