# Metodos aplicables a groupby
1. **Funciones de Agregación:**
   - Estas funciones se aplican a los grupos resultantes y resumen los datos. Algunas de las funciones de agregación más utilizadas son:
     - `.mean()`: Calcula la media de los valores en cada grupo.
     - `.min()`: Encuentra el valor mínimo en cada grupo.
     - `.max()`: Encuentra el valor máximo en cada grupo.
     - `.count()`: Cuenta el número de elementos en cada grupo.
     - `.sum()`: Calcula la suma de los valores en cada grupo.
     - `.std()`: Calcula la desviación estándar de los valores en cada grupo.
     - `.var()`: Calcula la varianza de los valores en cada grupo.

2. **Otras Operaciones:**
   - Además de las funciones de agregación, puedes realizar otras operaciones con `.groupby()`:
     - `.size()`: Devuelve el tamaño (número de filas) de cada grupo.
     - `.first()`: Devuelve la primera fila de cada grupo.
     - `.last()`: Devuelve la última fila de cada grupo.
     - `.nth(n)`: Devuelve la n-ésima fila de cada grupo.
     - `.apply(func)`: Aplica una función personalizada a cada grupo.

3. **Personalización y Creatividad:**
   - Puedes combinar múltiples operaciones y personalizar tus análisis según tus necesidades.
   - Experimenta con diferentes funciones y encuentra la que mejor se adapte a tus datos.

[Regresar a readme.md](readme.md)