# Proceso de Limpieza y Transformación de Datos

Este proceso detalla los pasos utilizados para la limpieza y transformación de datos antes de una fase de análisis exploratorio de redes en datos psicométricos. El proceso incluye la identificación de valores ausentes, la transformación de variables y la recodificación de ítems. A continuación se explican los pasos.

## 1. Limpieza de Datos

### Identificación y Eliminación de Valores Ausentes
1. **Carga de Datos**: 
   - Los datos se cargan desde un archivo Excel usando la función `read.xlsx()`.
   
2. **Detección de Valores Ausentes**: 
   - Se identifican los valores ausentes (NAs) en el conjunto de datos y se cuenta su número total.

3. **Creación de Subconjuntos**: 
   - Se crea un subconjunto que contiene solo las filas con valores ausentes y se almacena en una variable llamada `showna`.

4. **Conteo de Valores Ausentes por Fila**: 
   - Se calcula cuántos valores ausentes tiene cada fila en el subconjunto `showna` y se guarda en un nuevo conjunto de datos llamado `missing_by_rows`, que contiene el ID de la fila y el número de valores ausentes.

5. **Eliminación de Filas**: 
   - La mayoría de los valores ausentes están relacionados con el estado civil, por lo que se decide eliminar las filas afectadas. Después de esta operación, se vuelve a verificar la presencia de valores ausentes para confirmar la eliminación.

## 2. Transformación de Datos

### Transformación de Edad
1. **Corrección del Tipo de Dato**:
   - La variable "Edad" se convierte de texto a numérico.

2. **Detección y Corrección de Valores Inválidos**:
   - Se identifican valores no válidos como "1994", ".3", "&6", "6" y "5&". Estos valores se corrigen: el valor "1994" se reemplaza por 30 y los demás por la mediana de la edad (46).

3. **Imputación de Edad**: 
   - Si hay valores fuera del rango esperado (mayores de 100 o menores de 18 años) o valores ausentes, se reemplazan por la mediana de la variable.

### Recodificación de Ítems PHQ
1. **Ajuste de Escalas**:
   - Los ítems de la escala PHQ, que originalmente varían de 1 a 4, se recodifican para ajustarse a una escala de 0 a 3, utilizada en el estudio de referencia.

### Ítems Invertidos
1. **Identificación y Reversión de Ítems**:
   - Se identifican ítems que necesitan ser invertidos. 
   - Se realiza la inversión reemplazando el ítem original por su versión invertida. Luego, las columnas con los ítems originales son eliminadas.

## 3. Generación de Archivo CSV
- Los datos transformados se guardan en un archivo CSV llamado `data_cleaned.csv`.

## Observaciones
- Este script es crucial para preparar los datos antes del análisis de redes. La eliminación de valores ausentes y las transformaciones garantizan la calidad de los datos para análisis posteriores.
