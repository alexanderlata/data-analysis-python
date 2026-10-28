# Анализ данных с использованием языка Python

Материалы дисциплины «Анализ данных с использованием языка Python». 

Курс состоит из 16 семинаров и сквозного проекта, в котором каждый студент анализирует открытый набор данных.

## Содержание репозитория

| Папка или файл | Содержимое |
|---|---|
| `notebooks/` | ноутбуки семинаров: `seminar-NN-*.ipynb` |
| `homework/` | домашние задания по семинарам и файлы к ним |
| `project/` | этапы проекта на собственных юридических данных |
| `reference/` | справочники-шпаргалки |
| `datasets/` | наборы данных в формате CSV |
| `exercises/` | упражнения к семинарам: листок `seminar-NN-tasks.md` с формулировками и ноутбук `seminar-NN-tasks.ipynb` с заготовками и тестами |
| `syllabus.md` | календарный план |
| `how-to-install-Python.md` | установка Python и окружения курса |
| `environment.yml`, `requirements.txt` | окружение курса для conda и pip |
| `README.md` | этот файл |

## Семинары

| № | Тема | Ноутбук | Упражнения | Домашнее задание | Тесты и контрольные точки |
|---|---|---|---|---|---|
| 1 | Jupyter Lab, Markdown, первые задачи на Python | [seminar-01-tasks.ipynb](notebooks/seminar-01-tasks.ipynb) | в ноутбуке | [homework-01.md](homework/homework-01.md) | тест «Семинар 1»; дома: тесты «Проверка установки» и «Домашнее задание 1: функции» |
| 2 | NumPy: массивы, индексация, векторизация | [seminar-02-numpy-arrays.ipynb](notebooks/seminar-02-numpy-arrays.ipynb) | [листок](exercises/seminar-02-tasks.md), [ноутбук](exercises/seminar-02-tasks.ipynb) | [homework-02.md](homework/homework-02.md) | тест «Семинар 2» |
| 3 | NumPy: случайные выборки, статистика, пропуски, поиск и сортировка | [seminar-03-numpy-stats.ipynb](notebooks/seminar-03-numpy-stats.ipynb) | [листок](exercises/seminar-03-tasks.md), [ноутбук](exercises/seminar-03-tasks.ipynb) | [homework-03.md](homework/homework-03.md) | тест «Семинар 3» |
| 4 | Pandas: Series, DataFrame, загрузка и просмотр данных. Старт сквозного кейса | [seminar-04-pandas-basics.ipynb](notebooks/seminar-04-pandas-basics.ipynb) | [листок](exercises/seminar-04-tasks.md), [ноутбук](exercises/seminar-04-tasks.ipynb) | [homework-04.md](homework/homework-04.md) | тест «Семинар 4»; выдаётся этап 1 проекта |
| 5 | Pandas: фильтрация, сортировка, группировка, агрегация, сводные таблицы | [seminar-05-pandas-groupby.ipynb](notebooks/seminar-05-pandas-groupby.ipynb) | [листок](exercises/seminar-05-tasks.md), [ноутбук](exercises/seminar-05-tasks.ipynb) | [homework-05.md](homework/homework-05.md) | тест «Семинар 5» |
| 6 | Pandas: типы, даты, пропуски, объединение таблиц | [seminar-06-pandas-cleaning.ipynb](notebooks/seminar-06-pandas-cleaning.ipynb) | [листок](exercises/seminar-06-tasks.md), [ноутбук](exercises/seminar-06-tasks.ipynb) | [homework-06.md](homework/homework-06.md) | тест «Семинар 6»; сдача этапа 1 проекта; открывается тест «КР 1. Демовариант» |
| 7 | Контрольная работа № 1: NumPy и Pandas | [seminar-07-test-1.ipynb](notebooks/seminar-07-test-1.ipynb): правила и пустой ноутбук | | | КР 1: тест «КР 1» и задание «КР 1. Ноутбук» |
| 8 | Matplotlib и Seaborn: базовые графики и оформление | [seminar-08-matplotlib-seaborn.ipynb](notebooks/seminar-08-matplotlib-seaborn.ipynb) | [листок](exercises/seminar-08-tasks.md), [ноутбук](exercises/seminar-08-tasks.ipynb) | [homework-08.md](homework/homework-08.md) | тест «Семинар 8» |
| 9 | Seaborn и Plotly: распределения, связи, множественные графики | [seminar-09-seaborn-plotly.ipynb](notebooks/seminar-09-seaborn-plotly.ipynb) | [листок](exercises/seminar-09-tasks.md), [ноутбук](exercises/seminar-09-tasks.ipynb) | [homework-09.md](homework/homework-09.md) | тест «Семинар 9»; выдаётся этап 2 проекта |
| 10 | Предобработка данных: выбросы и пропуски | [seminar-10-outliers-missing.ipynb](notebooks/seminar-10-outliers-missing.ipynb) | [листок](exercises/seminar-10-tasks.md), [ноутбук](exercises/seminar-10-tasks.ipynb) | [homework-10.md](homework/homework-10.md) | тест «Семинар 10» |
| 11 | Проверка нормальности распределения | [seminar-11-normality.ipynb](notebooks/seminar-11-normality.ipynb) | [листок](exercises/seminar-11-tasks.md), [ноутбук](exercises/seminar-11-tasks.ipynb) | [homework-11.md](homework/homework-11.md) | тест «Семинар 11»; сдача этапа 2 проекта |
| 12 | Гипотеза о среднем: одна выборка и доверительные интервалы | [seminar-12-one-sample.ipynb](notebooks/seminar-12-one-sample.ipynb) | [листок](exercises/seminar-12-tasks.md), [ноутбук](exercises/seminar-12-tasks.ipynb) | [homework-12.md](homework/homework-12.md) | тест «Семинар 12»; выдаётся этап 3 проекта |
| 13 | Две выборки: t-тест, критерий Манна–Уитни, хи-квадрат | [seminar-13-two-samples.ipynb](notebooks/seminar-13-two-samples.ipynb) | [листок](exercises/seminar-13-tasks.md), [ноутбук](exercises/seminar-13-tasks.ipynb) | [homework-13.md](homework/homework-13.md) | тест «Семинар 13»; открывается тест «КР 2. Демовариант» |
| 14 | Контрольная работа № 2: визуализация, предобработка, гипотезы | [seminar-14-test-2.ipynb](notebooks/seminar-14-test-2.ipynb): правила и пустой ноутбук | | | КР 2: тест «КР 2» и задание «КР 2. Ноутбук»; сдача этапа 3 проекта |
| 15 | Разведочный анализ данных (EDA): структура отчёта и полный пример | [seminar-15-eda.ipynb](notebooks/seminar-15-eda.ipynb) | [листок](exercises/seminar-15-tasks.md), [ноутбук](exercises/seminar-15-tasks.ipynb) | [homework-15.md](homework/homework-15.md) | тест «Семинар 15»; выдаётся задание на защиту проекта |
| 16 | Защита проектов на собственных данных | [seminar-16-project-defense.ipynb](notebooks/seminar-16-project-defense.ipynb): регламент защиты, порядок выступлений, рубрика и лист вопросов | | | защита проекта: задание «Проект. Защита» |

## Календарный план

[syllabus.md](syllabus.md)

## Правила работы

Как работать с ноутбуком семинара: скачайте файл со страницы GitHub (кнопка скачивания справа вверху), откройте в Jupyter Lab, переименуйте в формате `Группа-Фамилия-Имя-seminar-NN.ipynb`. Упражнения к семинару лежат в папке `exercises/`: листок с формулировками и ноутбук с заготовками и тестами; они начинаются на паре и дорешиваются дома, ответы вводятся в тест Moodle. Что сдать и к какому сроку — в папке `homework/`.

## Проект на собственных данных

Сквозная линия курса: каждый студент находит открытый набор юридических данных и проходит с ним весь путь анализа. Набор один на весь проект, менять его после сдачи этапа 1 можно только по согласованию с преподавателем. Веса работ в итоговой оценке объявляет преподаватель на семинаре.

| Этап | Описание | Выдаётся | Сдаётся | Что сдать |
|---|---|---|---|---|
| 1. Поиск и описание данных | [project/01-data-search.md](project/01-data-search.md) | семинар 4 | семинар 6 | описание набора данных: источник, структура, переменные, исследовательские вопросы |
| 2. Разведочный анализ (EDA) | [project/02-eda.md](project/02-eda.md) | семинар 9 | семинар 11 | ноутбук: загрузка, пропуски, описательные статистики, корреляции, графики, выводы |
| 3. Проверка гипотез | [project/03-hypotheses.md](project/03-hypotheses.md) | семинар 12 | семинар 14 | ноутбук: не меньше четырёх гипотез разных видов — нормальность, одна выборка, две группы, связь категорий — с записью по формату и выводами |
| Защита | [project/04-defense.md](project/04-defense.md) | семинар 15 | семинар 16 | итоговый отчёт из этапов 2 и 3 и выступление на 5 минут |

### Контрольные точки

| Контрольная точка | Семинар | Что сдать |
|---|---|---|
| Проект, этап 1 | 6 | описание набора данных |
| Контрольная работа № 1 | 7 | тест «КР 1» и ноутбук |
| Проект, этап 2 | 11 | ноутбук разведочного анализа |
| Проект, этап 3 | 14 | ноутбук с проверкой гипотез |
| Контрольная работа № 2 | 14 | тест «КР 2» и ноутбук |
| Защита проекта | 16 | итоговый отчёт и выступление |

Веса контрольных точек в итоговой оценке объявляет преподаватель; баллы внутри каждого этапа — в его описании. Домашние задания по семинарам проверяются тестами Moodle и в таблицу не входят.

## Справочники

| Файл | О чём |
|---|---|
| [reference/numpy.md](reference/numpy.md) | функции и методы NumPy |
| [reference/pandas.md](reference/pandas.md) | pandas: структуры, загрузка, очистка, группировка, даты; выбросы и аномалии: асимметрия, правила IQR, трёх сигм и процентилей, медиана группы через `transform`, пять решений о выбросе и их цена |
| [reference/visualization.md](reference/visualization.md) | графики в matplotlib, seaborn и plotly: фигура и оси, линия, столбцы, гистограмма, ящик, тепловая карта, рассеяние, оформление, панели и сохранение; группы через `hue`, плотности, корреляции, доля и среднее с интервалом, панели одной командой, интерактивные графики и карта |
| [reference/statistics.md](reference/statistics.md) | scipy.stats и statsmodels: логика проверки гипотезы; нормальность — асимметрия и эксцесс, гистограмма с нормальной кривой, Q–Q график, тесты Шапиро–Уилка, Д’Агостино и Лиллиефорса, выборка для теста; одна выборка — t-тест и доверительный интервал для среднего, стандартная ошибка, знаковый ранговый тест Вилкоксона, z-тест и интервал Вилсона для доли, хи-квадрат согласия, поправка Бонферрони; две и больше выборок — t-тест Уэлча и d Коэна, критерий Манна–Уитни, парный t-тест и выравнивание по ключу, тест Вилкоксона для пар, ANOVA и Крускал–Уоллис, хи-квадрат независимости и V Крамера, точный тест Фишера, значимость корреляции Пирсона и Спирмена, таблица размеров эффекта |
| [reference/markdown.md](reference/markdown.md) | оформление текста в Markdown |

## Данные

Наборы данных лежат в папке [datasets](datasets/); описание файлов и переменных в [datasets/README.md](datasets/README.md). Сквозной юридический кейс курса — ДТП с пострадавшими в Брянской и Московской областях по данным ГИБДД, папка [datasets/legal](datasets/legal/) с описанием переменных; там же таблицы ДТП и участников Липецкой области для контрольных работ № 1 и № 2.

## Установка и запуск

1. Установите Python и библиотеки по инструкции [how-to-install-Python.md](how-to-install-Python.md): Miniconda, окружение `courses` и библиотеки курса.
2. Скачайте репозиторий: кнопка **Code → Download ZIP** на GitHub или
   ```bash
   git clone https://github.com/alexanderlata/data-analysis-python.git
   ```
3. Запустите Jupyter Lab из папки репозитория:
   ```bash
   conda activate courses
   jupyter lab
   ```

## Библиотеки

| Библиотека | Назначение |
|---|---|
| [numpy](https://numpy.org) | массивы и численные вычисления |
| [pandas](https://pandas.pydata.org) | таблицы и временные ряды |
| [matplotlib](https://matplotlib.org), [seaborn](https://seaborn.pydata.org), [plotly](https://plotly.com/python/) | визуализация |
| [scipy](https://scipy.org), [statsmodels](https://www.statsmodels.org) | статистика и проверка гипотез |
| [openpyxl](https://openpyxl.readthedocs.io) | чтение и запись Excel |

Минимальные версии библиотек указаны в [environment.yml](environment.yml) и [requirements.txt](requirements.txt).

## Вопросы

Вопросы и предложения по материалам: создайте Issue в этом репозитории или напишите преподавателю.
