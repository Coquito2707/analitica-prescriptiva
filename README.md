# Analitica Prescriptiva

## Descripcion

Este proyecto tiene como objetivo aplicar analitica prescriptiva usando un dataset de ventas de supermercado.

Primero se analizaron los datos de ventas, ganancias y descuentos. Despues se generaron recomendaciones para cada subcategoria de producto.

El sistema busca responder la pregunta:

**¿Que deberia hacerse?**

Para esto se sigue el flujo:

**Datos → Analisis → Resultado → Recomendacion → Accion**

## Dataset

El dataset contiene informacion de ventas de supermercado.

Algunas de las columnas utilizadas son:

- Order ID
- Customer Name
- Category
- Sub Category
- Order Date
- Sales
- Discount
- Profit
- Region
- State

El dataset contiene **9,994 registros y 11 columnas**.

## Limpieza de datos

Primero se revisaron valores nulos y filas duplicadas.

No se encontraron filas duplicadas.

Tambien se corrigio la columna `Order Date`, ya que las fechas venian en diferentes formatos. Para solucionarlo se uso `format="mixed"` y al final no quedaron fechas nulas.

## Analisis

Se analizaron principalmente:

- Ventas totales.
- Ganancias totales.
- Descuento promedio.
- Categorias.
- Subcategorias.

Despues se calcularon los promedios generales de ventas y ganancias.

Promedio de ventas:

`650303.57`

Promedio de ganancia:

`162918.31`

## Sistema de recomendaciones

El sistema compara las ventas y ganancias de cada subcategoria contra los promedios generales.

Se utilizaron las siguientes reglas:

- Ventas altas y ganancias altas → Aumentar disponibilidad.
- Ventas altas y ganancias bajas → Revisar costos o descuentos.
- Ventas bajas y ganancias altas → Mantener y promocionar.
- Ventas bajas y ganancias bajas → Reducir inventario o aplicar promocion.

Con estas reglas se genera automaticamente una recomendacion para cada subcategoria.

## Visualizacion

Se creo una grafica de ventas contra ganancias.

Tambien se agregaron lineas que representan el promedio de ventas y el promedio de ganancias.

Esto permite ver de forma visual en que zona se encuentra cada subcategoria y que recomendacion le corresponde.

## Resultado

El resultado final se guarda en:

`resultados/recomendaciones_finales.csv`

Este archivo contiene:

- Ventas.
- Ganancias.
- Descuento promedio.
- Recomendacion.

## Tecnologias utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook
- Visual Studio Code

## Instalacion

Crear un entorno virtual:

```bash
python -m venv .venv
```

Activar el entorno virtual en Windows:

```bash
.venv\Scripts\activate
```

Instalar las dependencias:

```bash
pip install -r requirements.txt
```

## Ejecucion

Abrir el archivo:

`notebooks/analisis_prescriptivo.ipynb`

Seleccionar el entorno virtual `.venv` como kernel y ejecutar las celdas en orden.

## Conclusion

Con este proyecto se aplico analitica prescriptiva para pasar de observar los datos a generar recomendaciones.

El sistema analiza las ventas y ganancias de cada subcategoria y propone una accion dependiendo de sus resultados.
