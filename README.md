#  Driver Drowsiness Detection System (NumPy Engine)

Sistema inteligente de prevención de accidentes viales diseñado para monitorear la fatiga en conductores mediante visión artificial y una red neuronal liviana programada en **NumPy**.

##  Características Principales
- **Extracción Biométrica:** Uso de MediaPipe Face Mesh para calcular **EAR** (Eye Aspect Ratio) y **MAR** (Mouth Aspect Ratio).
- **Procesamiento Temporal:** Análisis por ventanas continuas de **30 fotogramas** (~1 segundo) para diferenciar parpadeos normales de microsueños o bostezos.
- **Motor Propio (NumPy Engine):** Red neuronal denso-temporal ($60 \to 64 \to 1$) entrenada con Backpropagation puro en NumPy.
- **Enfoque de Alta Sensibilidad:** Implementación de penalización asimétrica (`peso = 2.5`) para maximizar la detección de la clase somnolienta.
- **Exportación Ligera:** Parámetros óptimos guardados en `pesos_red_somnolencia.json` para ejecución en tiempo real sin librerías pesadas.

## Métricas de Rendimiento (Test Set)
- **Sensibilidad (Recall):** `97.96%` *(48 de 49 casos de somnolencia detectados correctamente)*
- **Model Loss (Test):** `0.638`
- **Tasa de Falsos Negativos:** `< 2%`

## 🛠️ Tecnologías Utilizadas
- **Lenguaje:** Python 3.x
- **Visión Artificial:** OpenCV, MediaPipe
- **Procesamiento de Datos & IA:** NumPy, Scikit-Learn
- **Visualización:** Matplotlib, Seaborn

## Estructura del Pipeline
1. **Video Ingest** ➔ 2. **MediaPipe Landmark Extraction** ➔ 3. **EAR/MAR Normalization** ➔ 4. **30-Frame Windowing** ➔ 5. **NumPy NN Forward Pass** ➔ 6. **Alert Trigger**
