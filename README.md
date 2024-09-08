# Demo del Pipeline de Cálculo Automático de Balances de Energía EONTEC

En este proceso la ETL se encargará de extraer la información de dos fuentes (Google Drive y desde una API) de forma remota, posteriormente, la transformará a un formato manejable, la cruzará y filtrará, y finalmente la depositará o la disponibilizará para descarga en un destino para que los analistas o el regulador la usen.
Tambien se averigua la diferencia del plan vs lo real, y se puede obtener el valor de la energía generada real, vs la remanente que hace falta, y que hay que cubrir con contratos de energía.

"Si me sobra vendo la Energía, si me falta, la tengo que comprar"

## Fuentes
- Descarga Archivo de despacho horario de las centrales de energia consolidado
- Consumo de API de despacho programado para la fecha del ente regulador.
- Consumo de API de Precio de la energia por kWh para el día asignado
## Transformaciones
- Cambio de formato de Excel a Dataframe Pandas
- Cambio de formato de JSON a Dataframe Pandas de los datos de las API.
- Combinación de datos utilizando Pandas.
- Agregación, cálculos de los balances por unidad de generación (por planta)
- Identificación de operación: Compra o Venta.
## Transferencias o Cargas
- Carga por web a Bucket o Carpeta en la nube del regulador

## Stack de tecnologías

**Python (Pandas)**
- Simplicidad
- Familiaridad
- Rendimiento para pequeños volumenes
- Bajo costo (open source)

**Colab**

- Implementa procesos automáticos de respaldo, mediante scripts que sincronicen con Google Drive, además de que permite la mitigación de errores mediante la implementación de notebooks (paso a paso)
- Entorno de desarrollo serverless eficiente, entendible y fácil de manipular
- Completa integración con python

**Escalabilidad**

Integración con Dask: computación y procesamiento de datos distribuída (paralización) para medianos volumenes de datos.
