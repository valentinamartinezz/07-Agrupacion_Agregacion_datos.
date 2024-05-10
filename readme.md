# Agrupación y Agregación de Datos

### 1. ¿Qué es el método `.groupby()` en Pandas?
El método `.groupby()` en Pandas es una herramienta poderosa para obtener información significativa de tus datos. Funciona de manera similar al comando SQL `GROUP BY`. Básicamente, divide tus datos en grupos según una o más variables categóricas y luego aplica funciones de agregación a cada grupo. Esto te permite resumir y analizar datos de manera eficiente.

### 2. Ejemplo de Carga de Datos
Para ilustrar, carguemos un conjunto de datos de ventas ficticias utilizando Pandas:

```python
import pandas as pd

# Cargar datos de ventas (ejemplo)
df = pd.read_csv('https://raw.githubusercontent.com/datagy/data/main/sales.csv', parse_dates=['date'])
print(df.head())
```

Esto nos dará una vista previa de los primeros registros del DataFrame:

|       date | gender | region     | sales |
|------------|--------|------------|-------|
| 2022-08-22 | Male   | North-West | 20381 |
| 2022-03-05 | Male   | North-East | 14495 |
| 2022-02-09 | Male   | North-East | 13510 |
| 2022-06-22 | Male   | North-East | 15983 |
| 2022-08-10 | Female | North-West | 15007 |

### 3. Aplicando `.groupby()` y Funciones de Agregación
Ahora, veamos cómo agrupar los datos por la columna "region" y calcular la suma de las ventas para cada región:

```python
# Agrupar por región y sumar las ventas
sales_by_region = df.groupby('region')['sales'].sum()
print(sales_by_region)
```

Esto nos dará un resumen de las ventas totales por región.

[Otros metodos ademas de suma](metodos.md)

### 4. Uso de `.pivot_table()` para Análisis Multidimensional
Además de `.groupby()`, Pandas también ofrece `.pivot_table()` para realizar análisis multidimensional. Puedes usarlo para crear tablas dinámicas y resumir datos en función de múltiples variables.

- **¿Qué es `.pivot_table()`?**
   - `.pivot_table()` es un método en Pandas que nos permite crear tablas dinámicas (también conocidas como tablas cruzadas) a partir de un DataFrame.
   - Nos ayuda a resumir y analizar datos de manera más compleja que simplemente agrupar por una sola columna.

- **Sintaxis básica:**
   ```python
   df.pivot_table(values=None, index=None, columns=None, aggfunc='mean', fill_value=None)
   ```

   - `values`: La columna cuyos valores queremos resumir.
   - `index`: Las columnas que queremos usar como índices (filas) en la tabla dinámica.
   - `columns`: Las columnas que queremos usar como columnas en la tabla dinámica.
   - `aggfunc`: La función de agregación que queremos aplicar (por defecto es 'mean' para el promedio).
   - `fill_value`: Valor para rellenar celdas vacías.

- **Ejemplo de uso:**
   Supongamos que tenemos un DataFrame con datos de ventas y queremos crear una tabla dinámica para ver el promedio de ventas por género y región:

   ```python
   import pandas as pd

   # Crear un DataFrame de ejemplo
   data = {'gender': ['Male', 'Female', 'Male', 'Female'],
           'region': ['North-West', 'North-East', 'North-West', 'South-East'],
           'sales': [20381, 15007, 14495, 17500]}
   df = pd.DataFrame(data)

   # Crear la tabla dinámica
   pivot_result = df.pivot_table(values='sales', index='gender', columns='region', aggfunc='mean')

   print(pivot_result)
   ```

   Esto generará una tabla con el promedio de ventas para cada género y región:

   | region      | North-East | North-West | South-East |
   |-------------|------------|------------|------------|
   | Female      | 15007      | NaN        | 17500      |
   | Male        | 14495      | 20381      | NaN        |

- **Personalización y Creatividad:**
   - Puedes personalizar la tabla dinámica según tus necesidades, cambiando las columnas, funciones de agregación y valores.
   - Experimenta con diferentes combinaciones para obtener información relevante para tu análisis.


## Ejercicios
Del [dataset](https://www.kaggle.com/datasets/juanmerinobermejo/smartphones-price-dataset) realice las siguientes consignas:

1. **Agrupación por Marca y Promedio de Precios**
   Utiliza `groupby` para agrupar los smartphones por marca y calcula el precio promedio de cada una.

2. **Conteo de Modelos por Marca**
   Emplea `groupby` para contar la cantidad de modelos diferentes que tiene cada marca.

3. **RAM Promedio por Marca**
   Usa `groupby` para determinar la cantidad promedio de RAM para cada marca de smartphone.

4. **Tabla Pivot de Precios Máximos por Color**
   Crea una tabla pivot que muestre el precio máximo de los smartphones para cada color.

5. **Distribución de Almacenamiento por Marca**
   Con `groupby`, calcula la distribución de la capacidad de almacenamiento para cada marca.

6. **Precio Promedio por Combinación de RAM y Almacenamiento**
   Genera una tabla pivot que muestre el precio promedio para cada combinación única de RAM y almacenamiento.

7. **Cantidad de Smartphones Libres por Marca**
   Utiliza `groupby` para contar cuántos smartphones de cada marca están libres de contratos con compañías celulares.

8. **Precio Mínimo, Máximo y Promedio por Marca**
   Crea una tabla pivot que resuma el precio mínimo, máximo y promedio para cada marca de smartphone.

9. **Smartphones por Rango de Precios**
   Emplea `groupby` para agrupar los smartphones en rangos de precios y cuenta cuántos hay en cada rango.

10. **Comparación de Precios entre Smartphones Libres y con Contrato**
    Genera una tabla pivot que compare el precio promedio de los smartphones libres (`Free` = Yes) versus los que están atados a contratos (`Free` = No).
