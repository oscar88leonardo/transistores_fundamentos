# Material Didáctico: El Transistor Bipolar (BJT)
## Regiones de Operación, Circuitos de Aplicación, Simulaciones y Guía Docente

Este repositorio contiene el material docente digital interactivo desarrollado para la asignatura de **Fundamentos de Electrónica**, tomando como base el documento maestro [`Transistor.pdf`](file:///home/leonard0/Documentos/clases2026/Fundamentos%20de%20electr%C3%B3nica/HTML_SLIDES/Transistor.pdf).

---

## 📁 Archivos Desarrollados

| Archivo | Descripción | Formato / Características |
| :--- | :--- | :--- |
| **[`index.html`](file:///home/leonard0/Documentos/clases2026/Fundamentos%20de%20electr%C3%B3nica/HTML_SLIDES/index.html)** / **[`slides_transistor.html`](file:///home/leonard0/Documentos/clases2026/Fundamentos%20de%20electr%C3%B3nica/HTML_SLIDES/slides_transistor.html)** | **Slides interactivos para clase** con teoría, esquemas vectoriales SVG, fórmulas matemáticas en KaTeX y **3 laboratorios de simulación en tiempo real** incrustados. | HTML5, CSS3 Glassmorphism responsivo, Canvas interactivo, KaTeX. |
| **[`guia_ejercicios_transistor.html`](file:///home/leonard0/Documentos/clases2026/Fundamentos%20de%20electr%C3%B3nica/HTML_SLIDES/guia_ejercicios_transistor.html)** | **Guía de problemas y solucionario docente** con 8 ejercicios de aplicación resueltos paso a paso con datos comerciales (2N2222, 2N3904, 2N3906). Permite alternar entre **Modo Estudiante** (sin soluciones) y **Modo Docente** (con soluciones y rúbrica). | HTML5 imprimible a PDF (`@media print`), selector interactivo de perfil. |
| **[`guia_laboratorio_simulide.html`](file:///home/leonard0/Documentos/clases2026/Fundamentos%20de%20electr%C3%B3nica/HTML_SLIDES/guia_laboratorio_simulide.html)** | **Guía de Laboratorio Práctico con SimulIDE** basada en 6 circuitos reales con transistores (LDR, NTC, Temporizador RC, Multivibrador Astable, Par Darlington y Relé). Posee **alternancia de perfiles en vivo**: <br>&bull; **Versión Docente:** Solucionario completo con deducción analítica paso a paso y valores numéricos resueltos del Punto Q.<br>&bull; **Versión Estudiante:** Guía analítica estructurada para deducir mallas KVL/Thévenin y completar los cálculos para contrastar con SimulIDE.<br>&bull; **Esquemáticos Originales:** Incorpora las imágenes de esquemáticos oficiales de las fuentes de referencia ([Ángel Millán Cerdán](https://angelmicelti.github.io/4ESO/EAN/)), con el símbolo NPN y la flecha de emisor 100% nítidos. | HTML5 interactivo, KaTeX, imágenes oficiales de referencia, imprimible a PDF (`@media print`). |

---

## 🎯 Contenido de los Slides Interactivos

Las 14 diapositivas cubren sistemáticamente el temario oficial del documento:

1. **Slide 1 - Portada y Mapa Conceptual:** Panorama general de las tres regiones (Corte, Activa, Saturación) y su analogía con interruptores y amplificadores.
2. **Slide 2 - Estructura, Símbolos y BJT vs FET:** Comparativa de control por corriente vs voltaje, impedancias, velocidades, costos y convenciones NPN ($C \to E$) y PNP ($E \to C$).
3. **Slide 3 - Las Tres Regiones de Operación:** Tabla comparativa rigurosa con estados de unión BE y BC, voltajes característicos, criterios de saturación forzada ($k_{od} = 2 \text{ a } 5$) y disipación de potencia térmica ($P_D$).
4. **Slide 4 - Curvas Características y Recta de Carga DC:** Ecuación de la malla de colector, puntos extremos (Corte $V_{CE} = V_{CC}$, Saturación $I_{C(sat)} = V_{CC}/R_C$) y ubicación del punto Q.
5. **Slide 5 - [SIMULACIÓN #1] Laboratorio Virtual de Curvas y Recta de Carga:**
   - **Diagrama esquemático vectorial del circuito bajo prueba** (polarización fija con $V_{BB}, R_B, BJT, R_C, V_{CC}$).
   - Sliders en vivo para $V_{CC}$, $V_{BB}$, $R_B$, $R_C$ y $\beta$.
   - Trazado dinámico de la familia de curvas, la recta de carga y el punto $Q$.
   - Telemetría en tiempo real: $I_B$, $I_C$, $V_{CE}$, $P_D$ y badge dinámico de región.
6. **Slide 6 - Circuito de Aplicación 1: Conmutador Digital NPN (Low-Side):**
   - Interfaz con microcontroladores (Arduino/ESP32 a 3.3V / 5V).
   - Metodología de cálculo para saturación profunda.
   - Protección inductiva crítica mediante diodo Flyback en antiparalelo.
7. **Slide 7 - Circuito de Aplicación 2: Conmutador PNP High-Side vs NPN:**
   - Análisis de niveles de disparo y la **Regla de Oro** (Slide 16 de `Transistor.pdf`).
   - Demostración de por qué NPN es estándar para Low-Side y PNP para High-Side.
8. **Slide 8 - Circuito de Aplicación 3: Sensores Crepusculares con LDR:**
   - Comparativa analítica entre circuito *Darkness-Activated* (luz de noche) y *Light-Activated* (detector de día).
   - Comportamiento del divisor de voltaje con la fotorresistencia ($R_{LDR}$ de $\approx 500\ \Omega$ a $>100\text{ k}\Omega$).
9. **Slide 9 - [SIMULACIÓN #2] Laboratorio Virtual del Sensor con LDR:**
   - **Diagrama esquemático vectorial del circuito del sensor** (divisor $R_1$/LDR acoplado a la base del BJT con lámpara en colector).
   - Control deslizante de iluminación ambiental (de 0 Lux noche a 1000 Lux pleno sol).
   - Alternancia entre modo *Darkness-Activated* y *Light-Activated*.
   - Visualización gráfica de la bombilla encendiéndose/apagándose y telemetría de transición corte/saturación.
10. **Slide 10 - Región Activa y Transistor como Amplificador:**
    - Configuración en Emisor Común (CE).
    - Desfase de $180^\circ$ entre entrada y salida.
    - Función de los capacitores de desacoplo y acople de señal AC.
11. **Slide 11 - Polarización del Punto Q y Distorsión por Recorte (Clipping):**
    - Fenómeno de recorte por saturación (aplanamiento del valle de $V_{CE}$).
    - Fenómeno de recorte por corte (aplanamiento del pico en $V_{CC}$).
    - Criterio de máxima excursión simétrica no distorsionada ($V_{CEQ} \approx V_{CC}/2$).
12. **Slide 12 - [SIMULACIÓN #3] Osciloscopio Virtual de Amplificación y Recorte:**
    - **Diagrama esquemático vectorial del amplificador Emisor Común** (polarización universal por divisor, acople AC de entrada $v_{in}(t)$ y salida $v_{out}(t)$).
    - Ajuste interactivo del punto $V_{CEQ}$, ganancia y amplitud de la señal senoidal.
    - Visualización en trazo de osciloscopio en tiempo real con líneas de umbral de corte y saturación.
13. **Slide 13 - Otras Aplicaciones Lineales:**
    - Fuente de Corriente Constante con diodo Zener (Current Sink).
    - Buffer / Seguidor de Emisor (Colector Común) para adaptación de impedancias.
14. **Slide 14 - Resumen Metodológico y Algoritmo de Resolución:**
    - Árbol de decisión sistemático paso a paso para resolver cualquier circuito BJT.
    - Atajos de teclado e hipervínculo directo a la **Guía de Ejercicios de Práctica**.

---

## ⌨️ Atajos de Teclado en los Slides

- **Flecha Derecha ($\rightarrow$) / Barra Espaciadora / Page Down:** Siguiente diapositiva.
- **Flecha Izquierda ($\leftarrow$) / Page Up:** Diapositiva anterior.
- **F:** Activar / Desactivar pantalla completa para proyector o monitor.
- **T:** Abrir / Cerrar el menú lateral con el índice de diapositivas.
- **Esc:** Cerrar menús emergentes.

---

## 📝 Guía de Ejercicios y Solucionario Docente

El archivo [`guia_ejercicios_transistor.html`](file:///home/leonard0/Documentos/clases2026/Fundamentos%20de%20electr%C3%B3nica/HTML_SLIDES/guia_ejercicios_transistor.html) incluye **8 problemas completos con datos comerciales**, cada uno con su **esquemático circuital técnico en fondo blanco y trazos negros** (estilo libro clásico de ingeniería):

1. **Ejercicio 1:** Dimensionamiento de driver NPN para relé con microcontrolador (saturación forzada $k_{od} = 3$, disipación y diodo flyback). *Esquemático: Figura 1.1*.
2. **Ejercicio 2:** Conmutador High-Side con transistor PNP y el problema de niveles de voltaje con microcontroladores (solución con etapa previa NPN). *Esquemático: Figura 2.1*.
3. **Ejercicio 3:** Diseño de sensor crepuscular automático con LDR y potenciómetro de calibración para umbral de 20 Lux. *Esquemático: Figura 3.1*.
4. **Ejercicio 4:** Trazado analítico de la recta de carga estática DC y determinación de punto Q en polarización fija. *Esquemático: Figura 4.1*.
5. **Ejercicio 5:** Polarización por divisor de tensión y análisis de sensibilidad térmica ante cambios del $150\%$ en $\beta$. *Esquemático: Figura 5.1*.
6. **Ejercicio 6:** Cálculo de máxima excursión simétrica pico a pico ($V_{opp}$) y diagnóstico del tipo de recorte (clipping) en amplificadores AC. *Esquemático: Figura 6.1*.
7. **Ejercicio 7:** Fuente de corriente constante de $20\text{ mA}$ para LEDs con diodo Zener y cálculo del voltaje de cumplimiento en región activa. *Esquemático: Figura 7.1*.
8. **Ejercicio 8:** Diagnóstico de averías de laboratorio (*Troubleshooting*) a partir de tablas de voltajes de nodo medidos con multímetro. *Esquemático: Figura 8.1*.

### Modos de Visualización:
- **Vista Estudiante:** Oculta las soluciones para imprimir o compartir como taller de clase evaluable.
- **Vista Docente:** Despliega el solucionario completo paso a paso, mallas KVL, justificación de hipótesis, notas pedagógicas de errores comunes y la **Rúbrica Analítica de Evaluación**.
- **Impresión a PDF:** Optimizado con hoja de estilo CSS `@media print` para exportar a PDF limpio y profesional sin bordes oscuros.

---

## 🔬 Guía de Laboratorio con SimulIDE (`guia_laboratorio_simulide.html`)

El documento [`guia_laboratorio_simulide.html`](file:///home/leonard0/Documentos/clases2026/Fundamentos%20de%20electr%C3%B3nica/HTML_SLIDES/guia_laboratorio_simulide.html) es una **guía experimental completa de 6 prácticas** para el simulador libre **SimulIDE**, basada en los circuitos educativos de [Ángel Millán Cerdán (angelmicelti.github.io)](https://angelmicelti.github.io/4ESO/EAN/index.html).

Cada práctica incluye su **esquemático vectorial en fondo blanco y líneas negras**, deducción analítica rigurosa del **punto Q de polarización ($V_{CEQ}, I_{CQ}, I_{BQ}$)** en mallas de entrada/salida, guía paso a paso de armado en SimulIDE, tabla de recolección de mediciones y preguntas de análisis crítico:

1. **Práctica 1 - Detector de Oscuridad Básico ([detector_de_oscuridad.html](https://angelmicelti.github.io/4ESO/EAN/detector_de_oscuridad.html)):**  
   Divisor de tensión con LDR en rama inferior y transistor NPN. Cálculo de $Q_{luz}$ en corte ($9\text{ V}, 0\text{ mA}$) y $Q_{osc}$ en saturación ($0.2\text{ V}, 21.2\text{ mA}$).
2. **Práctica 2 - Ventilador Activado por NTC ([ventilador_activado_por_ntc.html](https://angelmicelti.github.io/4ESO/EAN/ventilador_activado_por_ntc.html)):**  
   Termistor NTC en rama superior para conmutación térmica de motor DC ($12\text{ V}, 80\text{ mA}$). Análisis de punto Q en reposo ($5.8\text{ V}$, activa insuficiente) y con calor ($0.2\text{ V}$, saturación plena). Verificación del diodo flyback contra sobretensiones.
3. **Práctica 3 - Temporizador RC ([temporizador.html](https://angelmicelti.github.io/4ESO/EAN/temporizador.html)):**  
   Circuito de retardo a la desconexión con condensador de $470\ \mu\text{F}$. Seguimiento dinámico del punto Q en SimulIDE (saturación $\to$ activa $\to$ corte) y cálculo del tiempo de retardo $t_{off} \approx \tau \cdot \ln(V_{CC}/0.7\text{ V}) \approx 56\text{ s}$.
4. **Práctica 4 - Multivibrador Astable ([multivibrador_astable.html](https://angelmicelti.github.io/4ESO/EAN/multivibrador_astable.html)):**  
   Oscilador simétrico a dos transistores con luces alternantes. Medición con el osciloscopio virtual de SimulIDE de las ondas cuadradas en colector, cálculo de periodos $T_1 = T_2 = 0.693 R_B C$ ($f \approx 0.7\text{ Hz}$) y alternancia de puntos Q.
5. **Práctica 5 - Par Darlington ([par_darlington.html](https://angelmicelti.github.io/4ESO/EAN/par_darlington.html)):**  
   Sensor táctil con ganancia compuesta $\beta_D \approx \beta_1 \cdot \beta_2 \approx 22,500$. Demostración analítica y experimental de las particularidades del punto Q en Darlington: $V_{BE,D} \approx 1.4\text{ V}$ y $V_{CE(sat),D} \approx 0.9\text{ V}$.
6. **Práctica 6 - Detector con Activación de Relé ([detector_de_oscuridad_con_activacin_de_rel.html](https://angelmicelti.github.io/4ESO/EAN/detector_de_oscuridad_con_activacin_de_rel.html)):**  
   Interfaz de potencia para lámparas de $230\text{ V}$ AC con bobina de relé ($400\ \Omega$) y diodo de libre circulación 1N4007. Cálculo analítico de saturación forzada ($I_B \ge 2.95\text{ mA}$) para evitar arco y vibración de contactos.
