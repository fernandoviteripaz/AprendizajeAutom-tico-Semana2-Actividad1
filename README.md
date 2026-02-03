# Clasificación de Intención de Compra en Redes Sociales

## Resumen del Problema
Este proyecto utiliza técnicas de Machine Learning para predecir si un usuario comprará un producto tras ver un anuncio. Es un problema de **clasificación binaria** donde analizamos si factores como la edad y el salario influyen en la decisión final.

## Metodología y Preprocesamiento
Para garantizar la precisión de los modelos, se aplicó el siguiente flujo:
1. **Limpieza:** Eliminación de identificadores irrelevantes (`User ID`).
2. **Codificación:** Transformación de la variable categórica `Gender` a numérica - 0 = Femenino, 1 = Masculino.
3. **Escalado:** Aplicación de `StandardScaler`. Esto es vital para **SVM**, ya que evita que el salario (valores altos) opaque a la edad (valores bajos) en el cálculo de distancias.
4. **Validación:** División del dataset en 80% entrenamiento y 20% prueba.

## Modelos Implementados
Se compararon tres enfoques:
* **Árbol de Decisión:** Útil para entender las reglas lógicas de compra.
* **SVM:** Para capturar fronteras de decisión complejas y no lineales.
* **Random Forest:** Reduce el sobreajuste y mejora la estabilidad.

## Resultados y Conclusiones
| Modelo | Accuracy | F1-Score |
| Árbol de Decisión | 0.85 | 0.82 |
| SVM (RBF) | **0.91** | **0.89** |
| Random Forest | 0.89 | 0.87 |

**Conclusión técnica:** El modelo **SVM** superó a los demás, demostrando que la relación entre edad y salario no es lineal. La **Edad** resultó ser el factor de mayor peso según el análisis de importancia de variables.
