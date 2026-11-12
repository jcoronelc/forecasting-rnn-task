1) CNN para clasificacion de audio - CREMA D
2) Opcion
   - Aplicar una CNN para clasificacion de texto
   - RNN para un problma de series temporales


Pronóstico *Day-Ahead* de Paute-Molino (Multivariado a Univariado) — *La más recomendada*
* **Problema:** Predecir la generación horaria de la central hidroeléctrica principal del país para el día siguiente.
* **Variable objetivo ($y$):** `Energía_Molino` a $t+24$ horas (o secuencia de 24 pasos futuros).
* **Entradas ($X$):**
  * Histórico de generación de las 4 centrales (`Energía_Mazar`, `Molino`, `Sopladora`, `Minas_San_Francisco`).
  * Número de unidades operativas en línea (`Unidades_*`).
  * Variables de calendario: hora del día (0–23) y día de la semana (seno/coseno).
* **Justificación técnica:** Mazar está aguas arriba de Molino y Sopladora en la cuenca del Paute. Existe una dependencia física y temporal directa: el volumen turbinado en Mazar influye con retardo en la disponibilidad de agua en Molino. La RNN modela este desfase temporal de forma natural.
* **Parámetros sugeridos:** Ventana de entrada (*lookback*) de 72 horas $\rightarrow$ horizonte de predicción de 24 horas.

