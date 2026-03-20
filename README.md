# 📈 Análisis de Dominio y Eficiencia en Tennis Clash

Este proyecto se centra en el análisis de datos de tenistas del juego móvil *Tennis Clash* para determinar su 'Índice de Dominio' y 'Eficiencia Relativa'. El objetivo es identificar qué tenistas ofrecen la mayor ventaja competitiva según una fórmula personalizada, y cómo gestionar los 'Trofeos' para optimizar el rendimiento y el emparejamiento (Matchmaking).

## 📋 Contenido del Repositorio

Este repositorio contiene el código y los análisis realizados en un entorno de Google Colab, que incluye:

1.  **Cálculo del Índice de Dominio Inicial (P^2.5 / T):** Se utiliza una fórmula para clasificar a los tenistas. Se calcula la eficiencia relativa en porcentaje.
2.  **Análisis de Eficiencia Relativa:** Se segmenta a los tenistas en clusters de alta, media y baja rentabilidad, y se extraen conclusiones estratégicas sobre la gestión de cada uno.
3.  **Plan de Acción: Reequilibrio de Trofeos:** Se calcula la 'deuda de trofeos' de cada tenista para alcanzar un 80% de la eficiencia máxima, identificando cuántos trofeos deben 'perder' para optimizar su rendimiento.
4.  **Visualización del Plan de Reequilibrio:** Un gráfico de barras que muestra visualmente la prioridad de ajuste de trofeos para cada tenista.
5.  **Fórmula Refinada (P^4.0 / T):** Se aplica una nueva fórmula de dominio para aumentar la sensibilidad a la Potencia.
6.  **Visualización de Clusters de Eficiencia:** Un scatter plot interactivo que relaciona Potencia, Trofeos e Índice de Dominio, permitiendo identificar patrones y la ubicación de cada tenista en el espectro de eficiencia.

## 📐 Fórmulas Utilizadas

### 1. Índice de Dominio (Versión 1)

La primera iteración de la fórmula de dominio se basa en la potencia del tenista elevada a 2.5, dividida por la cantidad de trofeos:

$D = \frac{\text{Potencia}^{2.5}}{\text{Trofeos}}$

### 2. Índice de Dominio (Versión Refinada)

Una versión posterior y más sensible a la potencia, elevándola a la cuarta potencia:

$D = \frac{\text{Potencia}^{4.0}}{\text{Trofeos}}$

### 3. Eficiencia Relativa (%)

La eficiencia de cada tenista se calcula como un porcentaje del Índice de Dominio máximo encontrado en el dataset:

$\text{Eficiencia}\_\% = \left( \frac{\text{Indice}\_\text{Dominio}}{\text{Indice}\_\text{Dominio}_{\text{max}}} \right) \times 100$

### 4. Trofeos Objetivo (T_Target) y Deuda de Trofeos (Delta_T)

Se calcula la cantidad ideal de trofeos ($T_{\text{Target}}$) que un tenista debería tener para alcanzar un 'target benchmark' de eficiencia (por ejemplo, el 80% del `Indice_Dominio` máximo). La 'Deuda de Trofeos' (${\Delta}T$) es la diferencia entre los trofeos actuales y los trofeos objetivo:

$T_{\text{Target}} = \frac{\text{Potencia}^{2.5}}{\text{Target Benchmark}}$

${\Delta}T = \text{Trofeos} - T_{\text{Target}}$

## 🚀 Conclusiones Clave y Estrategias

*   **La Paradoja de la Potencia:** Se observa que la **potencia bruta no es el único factor de éxito**. Tenistas con muy alta potencia (ej. N. Osaka) pueden ser ineficientes si sus trofeos son desproporcionadamente altos, lo que les empareja con oponentes muy fuertes.
*   **Gestión de MMR:** La clave para maximizar la eficiencia y el 'win-rate' en Tennis Clash es una gestión inteligente de los trofeos, manteniéndolos en un rango óptimo en relación con la potencia del tenista.
*   **Priorización del Reequilibrio:** El análisis identifica a los tenistas con mayor 'Deuda de Trofeos', indicando una **prioridad crítica para reducir sus trofeos** (mediante derrotas controladas en tours bajos) y así optimizar su Índice de Dominio.
*   **Clusters de Eficiencia:** La visualización de clusters permite agrupar a los tenistas por su combinación de Potencia y Trofeos, ofreciendo una visión clara de quiénes son los 'farmers' más rentables y quiénes requieren un ajuste estratégico.

## 🛠️ Tecnologías

*   Python 3
*   Pandas (para manipulación de datos)
*   Matplotlib & Seaborn (para visualización de datos)
*   Google Colab (entorno de desarrollo)

## 👨‍💻 Cómo Usar

1.  Abre el archivo `.ipynb` en Google Colab.
2.  Ejecuta las celdas en orden para replicar el análisis.
3.  Modifica los parámetros (ej. factor de potencia, porcentaje de reducción de trofeos) para experimentar con diferentes escenarios.
