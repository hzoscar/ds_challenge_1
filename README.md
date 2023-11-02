# Trading Bot - Proyecto Alura Latam

Este proyecto es parte del primer bootcamp en Data Science de Alura Latam.

En este proyecto, construí un robot de trading en Python capaz de tomar decisiones de compra y venta de Bitcoin en tiempo real. La decisión final se basa en la evaluación de cuatro indicadores. Para llevar a cabo este proyecto,utilicé Google Colaboratory. El proyecto se divide en seis partes:

## 1. Configuración del Entorno
En esta sección, se encuentra la información sobre la instalación de las bibliotecas necesarias y su importación.

## 2. Obtención de Datos
Aquí se describe cómo se obtuvieron los datos históricos de precios de Bitcoin utilizando una API en formato JSON. Se considera un período de los últimos 7 días con intervalos de 5 minutos. Además, se realiza web scraping en un sitio web para obtener el precio actual y algunos indicadores de tendencia de Bitcoin. Una vez que tenemos los datos históricos, se cargan en un DataFrame de Pandas para su manipulación y análisis. También hemos creado dos columnas, SMA20 y SMA100 (medias móviles), que se utilizan en uno de los indicadores.

## 3. Limpieza de Datos
En esta sección, se explica cómo se identificaron y se eliminaron valores atípicos, así como cómo tratar los valores nulos o duplicados en la base de datos. Todo esto se hace para calcular el precio promedio de Bitcoin.

## 4. Toma de Decisiones
El algoritmo de toma de decisiones se basa en cuatro indicadores.

- **Indicador 1:** Se compara el precio actual y la tendencia del Bitcoin (obtenida mediante web scraping) con el precio promedio calculado anteriormente. Si el precio actual es mayor o igual que la media y la tendencia es a la baja, se debe vender. Si el precio actual es menor que la media y la tendencia es alcista, se debe comprar.

- **Indicador 2:** Se utilizan las medias móviles creadas en el paso anterior. Se generan señales de compra cuando la SMA a corto plazo (SMA20) cruza por encima de la SMA a largo plazo (SMA100), lo que indica una posible tendencia alcista. Las señales de venta se producen cuando la SMA20 cruza por debajo de la SMA100, lo que sugiere una posible tendencia bajista.

- **Indicador 3:** Este indicador se basa en las Bandas de Bollinger. Las decisiones de compra, venta o espera se toman en función de la posición actual del precio con respecto a las Bandas de Bollinger, que se generan utilizando la librería TALIB.

- **Indicador 4:** Calculamos el RSI y se determina si comprar, vender o esperar en función de los valores del RSI y de los niveles de sobrecompra (70) y sobreventa (30) especificados.

## 5. Visualización
Se utilizan las bibliotecas Matplotlib y Chart Studio para crear un gráfico de velas (candlestick chart) con las últimas 100 observaciones, junto con gráficos individuales para cada indicador. También se incluye un mensaje en el gráfico que indica "Vender", "Comprar" o "" según la decisión del algoritmo.

## 6. Automatización
Finalmente, se automatiza el proceso. Se utiliza la librería de Python "time" para ejecutar el algoritmo de toma de decisiones cada 5 minutos y actualizar el gráfico.


## Colaboradores

- Alura Latam!
- [@ElProfeAlejo](https://github.com/ElProfeAlejo)
- [@christianpva](https://github.com/christianpva)

¡Gracias por visitar mi proyecto!


