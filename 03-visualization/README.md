# Визуализация с Seaborn & Matplotlib

Библиотека [`seaborn`](https://seaborn.pydata.org) позволяет визуализировать статистические данные и быстро строить широкий спектр 2D графиков.

Библиотека [`matplotlib`](https://matplotlib.org) позволяет строить широкий спектр графиков.

Базовые графики:

- диаграмма рассеяния, в том том числе с подогнанной кривой (scatter plot)
- линейная диаграмма (line plot)
- гистограмма (histogram)
- столбчатая диаграмма (bar chart)
- коробчатая диаграмма, "ящик с усами" (box plot)
- круговая/кольцевая диаграмма (pie/doughnut chart)
- температурная диаграмма (heatmap)
- пузырькова диаграмма (bubble chart, фактически частный случай рассеяния)

## Библиотека Seaborn

`import seaborn as sns`

Основные методы `seaborn`

|График|Метод|Ссылка|
|-|-|-|
|диаграмма рассеяния|`.scatterplot()`|[ссылка](https://seaborn.pydata.org/generated/seaborn.scatterplot.html#seaborn.scatterplot)|
|диаграмма рассеяния с регрессией|`.regplot()`|[ссылка](https://seaborn.pydata.org/generated/seaborn.regplot.html#seaborn.regplot)|
|как выше, но с разбивкой по сетке |`.lmplot`|[ссылка](https://seaborn.pydata.org/generated/seaborn.lmplot.html#seaborn.lmplot)|
|линейная диаграмма|`.lineplot()`|[ссылка](https://seaborn.pydata.org/generated/seaborn.lineplot.html#seaborn.lineplot)|
|гистограмма|`.histplot()`|[ссылка](https://seaborn.pydata.org/generated/seaborn.histplot.html#seaborn.histplot)|
|столбчатая диаграмма|`.histplot()`|[ссылка](https://seaborn.pydata.org/generated/seaborn.histplot.html#seaborn.histplot)|
|коробчатая диаграмма|`.boxplot()`|[ссылка](https://seaborn.pydata.org/generated/seaborn.boxplot.html#seaborn.boxplot)|
|температурная диаграмма|`.heatmap()`|[ссылка](https://seaborn.pydata.org/generated/seaborn.heatmap.html#seaborn.heatmap)|

Общие параметры графиков

|Параметр|Описание|
|-|-|
|`x,y`|переменные по осям|
|`hue`|от какой переменной будет зависеть цвет|
|`size`|от какой переменной будет зависеть размер|
|`style`|от какой переменной будет зависеть форма точки|
|`marker(s)`|форма точки|

## Библиотека Matplotlib

`import matplotlib.pyplot as plt`

|График|Метод|Ссылка|
|-|-|-|
|2d диаграмма рассеяния с регрессией|`.scatter()`|[ссылка](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.scatter.html)|
|линейная диаграмма|`.plot()`|[ссылка](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.plot.html)|
|гистограмма|`.hist()`|[ссылка](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.hist.html)|
|столбчатая диаграмма|`.bar()`|[ссылка](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.bar.html)|
|коробчатая диаграмма|`.boxplot()`|[ссылка](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.boxplot.html)|
|круговая|`.pie()`|[ссылка](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.pie.html#matplotlib.pyplot.pie)|
|температурная карта|`.imshow()`|[ссылка](hhttps://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.imshow.html#matplotlib.pyplot.imshow)|

**Замечание**: интерфейс для построение графиков в `matplotlib`

название рисунка `plt.title()`

добавить легенду `plt.legend()`

отобразить рисунок `plt.show()`

## Библиотека Plotly

`import plotly.express as px`

|График|Метод|Ссылка|
|-|-|-|
|2d диаграмма рассеяния с регрессией|`.scatter()`|[ссылка](https://plotly.com/python/line-and-scatter)|
|линейная диаграмма|`.line()`|[ссылка](https://plotly.com/python/line-and-scatter)|
|гистограмма|`.histogram()`|[ссылка](https://plotly.com/python/histograms/)|
|столбчатая диаграмма|`.bar()`|[ссылка](https://plotly.com/python/bar-charts/)|
|коробчатая диаграмма|`.box()`|[ссылка](https://plotly.com/python/box-plots/)|
|круговая|`.pie()`|[ссылка](https://plotly.com/python/pie-charts/)|
|температурная карта|`.imshow()`|[ссылка](https://plotly.com/python/heatmaps/)|
|3d диаграмма рассеяния|`.scatter_3d()`|[ссылка](https://plotly.com/python/line-and-scatter)|

**Замечание**: интерфейс для построение графиков в `plotly`

`fig = px.method()`

`# fig.update_layout()`

`fig.show()`