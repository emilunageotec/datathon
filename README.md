# Modelo de predicción para proyección de pasajeros y productos vendidos. Viva Aerobus DATATHON 2024
-------------
## Problemática
Predecir el volumen de pasajeros para a su vez, predecir la cantidad de productos vendidos en un vuelo y asegurar la existencia de los productos en cada vuelo y reducir el desperdicio de productos perecederos.

Fue necesario el uso de Python, Numpy, Scikit Learn, Pandas, Jupyter Notebooks.

## Metodología
- Exploración de Datos: Dentro de esta etapa analizamos lo modelos, posibles insights y limpiamos la base de datos.
- Construcción de modelos: En esta etapa probamos diferentes modelos y decidimos cual sería mejor
para las predicciones.
- Predicciones: Realizamos las predicciones de pasajeros y de productos necesarios.

## Datos disponibles
- En el apartado de ventas se tiene información sobre el momento en el que se realizó la transacción, así como el vuelo en el que sucedió la compra. El tipo de producto al que pertenece, el nombre del producto, la cantidad que se vendió, y por último, el total de dinero generado en ventas del producto.

- En la base de datos de los vuelos tenemos información importante como es la capacidad del avión, de que terminal a que terminal viaja, fecha y hora.

## Limpieza de datos
1. Búsqueda de datos nulos 
2. Transformacion de datos
3. Encoding de variables
4. Merge de columnas

## Encoding
Para poder trabajar variables como la terminal de la que sale y la terminal a la que llega cada vuelo, las fechas, el tipo de producto y la categoría. Hicimos un encoding a los datos para poder entrenar nuestros modelos de mejor manera.

## Exploración de datos
- Sobreventa de vuelos 
- Gran cantidad de vuelos con poca gente
- Productos vendidos más de 60000 veces y otros un total de 16
- Más vuelos en Julio, Agosto, Diciembre (31 días)

## Modelos
Para todas nuestras predicciones se optó por emplear el modelo de regresión de aprendizaje supervisado Random Forest.
- Bookings: Primero se empleó un Random Forest con un n_estimators = 10, max_depth = 30, criterios = “poisson”.
Obtuvimos un R^2 de 0.9992
- Pasajeros: Se empleó un Random Forest con hiperarámetros n_estimators = 10, max_depth = 30, criterios = “poisson”.
Obtuvimos un R^2 de 0.9997
- Ventas: Se empleó un Random Forest con hiperarámetros n_estimators = 20, max_depth = 30, criterios = “poisson”.
Obtuvimos un R^2 de 0.5612