# Sistema de análisis y búsqueda de estados para el sueño infantil (Tipo C)

## Descripción
Proyecto académico para el caso Tipo C: **Sueño en los Recién Nacidos**. El sistema representa estados sintéticos de familias usando cuatro variables: sueño continuo, despertares, fatiga de los padres y rutina. Calcula un costo de desviación, recorre estados y visualiza su evolución.

> **Uso educativo:** los datos son inventados. El costo es una fórmula demostrativa creada para la práctica, no una escala médica ni una recomendación de sueño infantil. El sistema no evalúa la salud de un bebé y no debe utilizarse para tomar decisiones de cuidado o tratamiento.

## Objetivo
Implementar en Python un espacio de estados, una estrategia de búsqueda inspirada en A*, una función de costo consistente y una visualización de variables para documentar el razonamiento computacional.

## Variables
| Variable | Símbolo | Descripción |
|---|---|---|
| Sueño continuo | `X1_Sueno` | Horas sintéticas de sueño continuo |
| Despertares | `X2_Despertarse` | Conteo simulado de despertares |
| Fatiga de padres | `X3_Fatiga` | Nivel sintético de fatiga, de 0 a 5 |
| Rutina | `X4_Rutina` | 0 = irregular, 1 = parcialmente estable, 2 = estable (escala ficticia) |
| Costo total | `Costo_Total` | Puntaje de desviación creado para el ejercicio |

## Función de costo
Se utiliza la misma fórmula en ambos notebooks:

`Costo_Total = max(0, (10 - X1_Sueno) * 15) + X2_Despertarse * 20 + X3_Fatiga * 15 + (2 - X4_Rutina) * 10`

Los valores y pesos son arbitrarios y solo sirven para practicar programación. El `max(0, ...)` evita que el componente de sueño se vuelva negativo si las horas superan 10.

## Archivos
- `README.md`: documentación del proyecto.
- `01_espacio_estados_busqueda_A_star.ipynb`: estados de familias, costo y selección del estado de menor costo.
- `02_pipeline_semanal_visualizacion.ipynb`: DataFrame semanal sintético, búsqueda por transiciones y gráficos de líneas.

## Cómo ejecutar
1. Crea un repositorio en GitHub llamado `tipo-c-sueno-infantil`.
2. Sube los tres archivos.
3. Abre los notebooks en Google Colab y ejecuta todas las celdas en orden.
4. Revisa los resultados impresos y las visualizaciones.

## Nota sobre A*
A* requiere definir estados, transiciones, costos de transición y una heurística. En el segundo notebook se muestra una búsqueda sobre una secuencia de estados y se explicita que la ruta disponible está limitada a los registros del DataFrame; no debe interpretarse como una solución clínica ni como una optimización real del sueño infantil.
