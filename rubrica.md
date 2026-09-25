# Rúbrica Oficial de Evaluación - Examen Final Noviembre 2026
**Universidad Católica de Santiago del Estero (UCSE) - Departamento Académico San Salvador (DASS)**  
**Carrera:** Tecnicatura Universitaria en Automatización y Robótica  
**Cátedra:** Informática (Algoritmos y Programación Estructurada con Python)  
**Condición de Aprobación:** Mínimo **60% (60 puntos = Nota 4 - cuatro)**  

---

## 1. Criterios Generales y Estructura Principal (10 Puntos)
*Obligatorio y común a ambos temas.*

| Ítem Evaluado | Puntaje | Detalle y Consideraciones |
| :--- | :---: | :--- |
| **Identificación del Alumno** | **2 pts** | Imprime Apellido y Nombre al inicio del programa. |
| **Menú Principal (`while`)** | **4 pts** | Menú interactivo con bucle `while` que presenta las 3 opciones exactas. |
| **Validación de Opción** | **2 pts** | Manejo de opciones fuera de rango (ej. 4, -1, 99) mostrando mensaje de error sin que el programa termine. |
| **Opción de Salida Limpia** | **2 pts** | La opción 3 rompe/finaliza el ciclo de manera prolija con mensaje de despedida. |

---

## 2. Tema 1: Telemetría y Actuadores de Celdas Robóticas

### Ejercicio 1: Calibración de Actuadores (45 Puntos) - Ciclo Exacto
*Evalúa el uso de ciclos determinados (`for` o `while` con contador), validación interna y acumuladores.*

| Criterio | Puntaje | Caso de Prueba / Regla de Corrección |
| :--- | :---: | :--- |
| **Estructura del Ciclo Exacto** | **15 pts** | Itera **exactamente 6 veces** (una por servomotor). Penalización de 0 pts si usa ciclo condicional. |
| **Validación Interna (`corriente > 0`)** | **10 pts** | Bucle interno `while` que no avanza al siguiente eje si se ingresa un valor `<= 0`. |
| **Acumulación y Promedio** | **10 pts** | Acumula la corriente total y calcula el promedio dividiendo entre 6 fuera del bucle. |
| **Salidas y Conteo de Alta Carga** | **10 pts** | Cuenta cuántos servomotores superaron los **850 mA**. Muestra total, promedio y conteo formateados. |

### Ejercicio 2: Telemetría de Baterías de la Flota AGV (55 Puntos) - Ciclo Indeterminado
*Evalúa ciclos condicionales con centinela, validación de rango, discriminación de estados y búsqueda de extremos.*

| Criterio | Puntaje | Caso de Prueba / Regla de Corrección |
| :--- | :---: | :--- |
| **Estructura de Parada por Centinela (-1)** | **15 pts** | Ciclo `while` que lee baterías hasta que se ingresa exactamente `-1`. El centinela no debe procesarse como un robot. |
| **Validación de Rango [0, 100]** | **10 pts** | Si se ingresa un valor distinto de -1 y fuera del intervalo [0, 100], avisa error y no altera contadores. |
| **Clasificación por Robot** | **10 pts** | Dictamina inmediatamente: `<20%` (Crítico), `20% a 50%` (Moderado), `>50%` (Óptimo). |
| **Búsqueda del Menor Valor (Mínimo)** | **10 pts** | Algoritmo correcto de menor valor para hallar la batería más baja registrada. |
| **Porcentaje de Críticos y Caso Límite** | **10 pts** | Calcula `(criticos / total) * 100`. Si el primer dato es `-1`, muestra `"No se registraron robots"` sin provocar `ZeroDivisionError`. |

---

## 3. Tema 2: Control de Calidad en Línea Automatizada

### Ejercicio 1: Test de Resistencia de Sensores Térmicos (45 Puntos) - Ciclo Exacto
*Evalúa ciclos determinados de 7 repeticiones, acumulación de tiempos y condicional evaluativo global.*

| Criterio | Puntaje | Caso de Prueba / Regla de Corrección |
| :--- | :---: | :--- |
| **Estructura del Ciclo Exacto** | **15 pts** | Itera **exactamente 7 veces** (un sensor por vuelta). |
| **Validación Interna (`tiempo > 0`)** | **10 pts** | Bucle interno `while` que rechaza valores `<= 0`. |
| **Acumulación y Promedio** | **10 pts** | Suma los tiempos y calcula el promedio dividiendo entre 7. |
| **Condicional de Alerta (> 15 ms)** | **10 pts** | Si promedio > 15 ms: `"ALERTA: La línea requiere recalibración"`; sino `"ESTADO NOMINAL"`. |

### Ejercicio 2: Inspección de Peso de Piezas Fabricadas (55 Puntos) - Ciclo Indeterminado
*Evalúa ciclos condicionales con centinela 0, rangos de tolerancia y detección del peso máximo.*

| Criterio | Puntaje | Caso de Prueba / Regla de Corrección |
| :--- | :---: | :--- |
| **Estructura de Parada por Centinela (0)** | **15 pts** | Ciclo `while` que finaliza al ingresar `0` (el cero no cuenta como pieza). |
| **Validación de No Negatividad (`peso >= 0`)**| **10 pts** | Rechaza valores negativos con mensaje de error sin incrementar contadores. |
| **Control de Tolerancia [480, 520]** | **10 pts** | Clasifica como Aceptada (480 a 520 inclusive) o Rechazada (fuera de rango). |
| **Búsqueda de la Pieza Más Pesada (Máximo)**| **10 pts** | Algoritmo correcto de mayor valor para determinar el peso máximo. |
| **Porcentaje de Rechazadas y Caso Límite** | **10 pts** | Calcula `(rechazadas / total) * 100`. Si el primer dato es `0`, muestra mensaje de lote vacío sin `ZeroDivisionError`. |

---

## 4. Escala de Conversión Numérica (Ordenanza Académica UCSE)

| Puntaje Logrado | Calificación Numérica | Condición Final |
| :---: | :---: | :---: |
| 0 a 39 pts | **1 o 2** | Desaprobado |
| 40 a 59 pts | **3** | Desaprobado |
| 60 a 69 pts | **4 (Cuatro)** | **Aprobado** (Mínimo exigible) |
| 70 a 74 pts | **5 (Cinco)** | Aprobado |
| 75 a 79 pts | **6 (Seis)** | Aprobado |
| 80 a 84 pts | **7 (Siete)** | Aprobado |
| 85 a 89 pts | **8 (Ocho)** | Aprobado |
| 90 a 95 pts | **9 (Nueve)** | Aprobado |
| 96 a 100 pts | **10 (Diez)** | Aprobado con Excelencia |

---

## 5. Tabla de Penalizaciones Frecuentes
- **-10% a -20%:** Si el programa se cuelga (termina abruptamente) ante ingresos inválidos o división por cero.
- **-20%:** Si se utilizó un ciclo condicional `while` libre en un ejercicio que exigía explícitamente ciclo exacto (`for` o contador fijo).
- **-10%:** Si no se validan los valores negativos en las entradas requeridas.
- **-5%:** Si el nombre del archivo entregado no sigue la convención `ApellidoNombre.py`.
