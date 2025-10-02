# Pandas: Справочник

## 1. Общее представление о Pandas

**История**: создана Уэсом МакКинни в 2008 году для работы с финансовыми данными. Название от "panel data".

**Ключевые особенности**: высокая производительность, интуитивный API, встроенные инструменты для обработки данных, интеграция с NumPy/Matplotlib/scikit-learn, работа с временными рядами.

**Области применения**: анализ данных (EDA), подготовка данных для ML, финансовый анализ, статистический анализ, визуализация, временные ряды, ETL-процессы.

## 2. Подключение библиотеки

`import pandas as pd`

`import numpy as np`

## 3. Основные структуры данных

### 3.1 Series - одномерный массив с метками

**Series** - одномерная структура с индексами, похожая на колонку таблицы или массив с метками.

|Свойство/Метод|Описание|
|-|-|
|`.values`|Значения Series как массив NumPy|
|`.index`|Объект индекса|
|`.dtype`|Тип данных|
|`.name`|Имя Series|
|`.head(n=5)`|Первые n элементов|
|`.tail(n=5)`|Последние n элементы|
|`.unique()`|Уникальные значения|
|`.value_counts()`|Частота значений|

**Создание Series:**

|Метод|Описание|
|-|-|
|`pd.Series(data)`|Из списка, массива, словаря|
|`pd.Series(data, index=labels)`|С явным указанием индекса|

### 3.2 DataFrame - двумерная табличная структура

**DataFrame** - двумерная таблица с метками для строк и столбцов. Строки (ось 0) - наблюдения, столбцы (ось 1) - переменные.

**Важно**: все элементы в столбце могут быть разных типов, но обычно одного типа.

**Важно**: пропущенные значения отображаются как `NaN` или `None`.

**Важно**: индексация начинается с нуля!

**Замечание**: большинство методов возвращает датафрейм. В скобках указаны значения аргументов по умолчанию.

|Свойство|Описание|
|-|-|
|`.shape`|Размер: (число строк, число столбцов)|
|`.index`|Индекс строк|
|`.columns`|Названия столбцов|
|`.dtypes`|Типы данных по столбцам|
|`.size`|Общее число элементов|
|`.ndim`|Число измерений (всегда 2)|
|`.T`|Транспонированный DataFrame|
|`.values`|Значения как массив NumPy|

**Создание DataFrame:**

|Метод|Описание|
|-|-|
|`pd.DataFrame(data)`|Из словаря, списка словарей, массива NumPy|
|`pd.DataFrame(data, index=None, columns=None)`|С явным указанием индекса и столбцов|

### 3.3 Index - объект индекса

**Index** - неизменяемая структура для хранения меток осей.

|Тип индекса|Описание|
|-|-|
|`RangeIndex`|Целочисленный индекс по умолчанию (0, 1, 2, ...)|
|`Int64Index`|Целочисленный индекс с явным указанием|
|`DatetimeIndex`|Индекс для временных рядов|
|`MultiIndex`|Иерархический/многоуровневый индекс|
|`CategoricalIndex`|Индекс для категориальных данных|

|Метод|Описание|
|-|-|
|`.set_index(keys, drop=True, inplace=False)`|Установить столбец(ы) как индекс|
|`.reset_index(drop=False, inplace=False)`|Сбросить индекс в столбец|
|`pd.date_range(start, end, periods, freq)`|Создать временной индекс|
|`pd.MultiIndex.from_tuples(tuples)`|Создать многоуровневый индекс|

## 4. Загрузка и сохранение данных

### 4.1 Чтение данных

|Функция|Формат|Основные параметры|
|-|-|-|
|`pd.read_csv(filepath)`|CSV|`sep=','`, `decimal='.'`, `encoding='utf-8'`, `header=0`, `index_col=None`, `usecols=None`, `nrows=None`, `skiprows=None`, `na_values=None`|
|`pd.read_excel(filepath)`|Excel|`sheet_name=0`, `header=0`, `index_col=None`, `usecols=None`, `engine='openpyxl'`|
|`pd.read_json(filepath)`|JSON|`orient='records'`, `lines=False`|
|`pd.read_sql(query, conn)`|SQL|`query` (SQL-запрос), `conn` (соединение с БД)|
|`pd.read_sql_query(query, conn)`|SQL|Выполнение SQL-запроса|
|`pd.read_sql_table(table_name, conn)`|SQL|Чтение всей таблицы|
|`pd.read_parquet(filepath)`|Parquet|`engine='auto'`, `columns=None`|
|`pd.read_hdf(filepath)`|HDF5|`key` (имя таблицы в файле)|
|`pd.read_pickle(filepath)`|Pickle|Бинарный формат Python|
|`pd.read_html(url)`|HTML|Извлечение таблиц из HTML|
|`pd.read_clipboard()`|Буфер|Чтение из буфера обмена|

### 4.2 Запись данных

|Метод|Формат|Основные параметры|
|-|-|-|
|`.to_csv(filepath)`|CSV|`sep=','`, `decimal='.'`, `encoding='utf-8'`, `index=True`, `header=True`, `na_rep='NA'`|
|`.to_excel(filepath)`|Excel|`sheet_name='Sheet1'`, `index=True`, `header=True`, `engine='openpyxl'`|
|`.to_json(filepath)`|JSON|`orient='records'`, `lines=False`, `force_ascii=True`|
|`.to_sql(table_name, conn)`|SQL|`if_exists='fail'` ('fail', 'replace', 'append'), `index=True`|
|`.to_parquet(filepath)`|Parquet|`engine='auto'`, `compression='snappy'`|
|`.to_hdf(filepath, key)`|HDF5|`key` (имя таблицы), `mode='a'`|
|`.to_pickle(filepath)`|Pickle|Бинарный формат Python|

## 5. Базовые операции с данными

### 5.1 Просмотр и навигация

|Метод|Описание|
|-|-|
|`.head(n=5)`|Первые n строк|
|`.tail(n=5)`|Последние n строк|
|`.sample(n=None, frac=None, random_state=None)`|Случайные n строк или доля frac|
|`.info()`|Информация о DataFrame (типы, пропуски, память)|
|`.describe(include=None, exclude=None)`|Описательная статистика (count, mean, std, min, 25%, 50%, 75%, max)|
|`.shape`|Размерность (строки, столбцы)|
|`.columns`|Названия столбцов|
|`.index`|Индекс строк|
|`.dtypes`|Типы данных по столбцам|
|`.size`|Общее число элементов|
|`.nunique()`|Число уникальных значений по столбцам|

### 5.2 Индексация и выбор данных

|Метод|Описание|Тип|
|-|-|-|
|`.loc[row_labels, col_labels]`|Выбор по меткам (включительно)|По меткам|
|`.iloc[row_positions, col_positions]`|Выбор по позициям (не включая конец)|По позициям|
|`df['column']`|Выбор одного столбца (Series)|Столбец|
|`df[['col1', 'col2']]`|Выбор нескольких столбцов (DataFrame)|Столбцы|
|`df[condition]`|Логическая индексация|Фильтрация|
|`.at[row_label, col_label]`|Быстрый доступ к одному значению по меткам|Скаляр|
|`.iat[row_position, col_position]`|Быстрый доступ к одному значению по позициям|Скаляр|

**Логические операторы для фильтрации:**

|Оператор|Описание|
|-|-|
|`&`|И (AND)|
|`\|`|ИЛИ (OR)|
|`~`|НЕ (NOT)|
|`.isin(values)`|Проверка на вхождение|
|`.between(left, right, inclusive='both')`|Проверка на вхождение в диапазон|
|`.str.contains(pattern)`|Проверка на содержание подстроки (для строк)|

### 5.3 Сортировка и фильтрация

|Метод|Описание|
|-|-|
|`.sort_values(by, ascending=True, inplace=False)`|Сортировка по значениям столбца(ов)|
|`.sort_index(ascending=True, inplace=False)`|Сортировка по индексу|
|`.query(expr)`|Фильтрация по строковому выражению|
|`.nlargest(n, columns)`|n наибольших значений|
|`.nsmallest(n, columns)`|n наименьших значений|

### 5.4 Работа со столбцами и строками

|Операция|Метод|Описание|
|-|-|-|
|Добавление столбца|`df['new_col'] = values`|Создать новый столбец|
|Добавление столбцов|`df[['col1', 'col2']] = values`|Создать несколько столбцов|
|Удаление столбцов|`.drop(columns=['col1', 'col2'], inplace=False)`|Удалить столбцы|
|Удаление столбца|`del df['column']`|Удалить столбец (на месте)|
|Удаление столбца|`.pop('column')`|Удалить и вернуть столбец|
|Удаление строк|`.drop(index=[0, 1, 2], inplace=False)`|Удалить строки по индексу|
|Переименование|`.rename(columns={'old': 'new'}, inplace=False)`|Переименовать столбцы/индекс|
|Переименование|`.columns = ['A', 'B', 'C']`|Присвоить новые имена столбцам|

## 6. Обработка пропущенных значений (NaN)

### 6.1 Обнаружение пропусков

|Метод|Описание|
|-|-|
|`.isnull()` или `.isna()`|Проверка на пропуски (True/False)|
|`.notnull()` или `.notna()`|Проверка на наличие значений (True/False)|
|`.isnull().sum()`|Количество пропусков по столбцам|
|`.isnull().any()`|Есть ли пропуски в столбцах|
|`.isnull().all()`|Все ли значения пропущены в столбцах|

### 6.2 Обработка пропусков

|Метод|Описание|Параметры|
|-|-|-|
|`.dropna(axis=0, how='any', inplace=False)`|Удаление строк/столбцов с пропусками|`axis=0` (0-строки, 1-столбцы), `how='any'` ('any', 'all'), `subset=None` (список столбцов), `thresh=None` (минимум непропущенных)|
|`.fillna(value, method=None, inplace=False)`|Заполнение пропусков|`value` (скаляр, словарь, Series), `method=None` ('ffill'/'pad', 'bfill'/'backfill')|
|`.interpolate(method='linear', inplace=False)`|Интерполяция пропусков|`method='linear'` ('linear', 'time', 'polynomial', и др.)|
|`.replace(to_replace, value, inplace=False)`|Замена значений|`to_replace` (значение или список), `value` (новое значение)|

**Стратегии заполнения:**

|Стратегия|Применение|
|-|-|
|Удаление (dropna)|Если пропусков мало (< 5%)|
|Константа (fillna)|Для категориальных данных|
|Среднее/медиана (fillna)|Для числовых данных|
|Мода (fillna)|Для категориальных данных|
|Forward/backward fill|Для временных рядов|
|Интерполяция|Для временных рядов|
|По группам (groupby + transform)|Заполнение по категориям|

## 7. Описательные статистики

### 7.1 Описательные статистики для числовых переменных/наблюдений

|Метод|Описание|Параметры по умолчанию|
|-|-|-|
|`.describe(percentiles=None, include=None, exclude=None)`|Полная описательная статистика|count, mean, std, min, 25%, 50%, 75%, max|
|`.min(axis=0, skipna=True, numeric_only=False)`|Минимум вдоль оси axis|`axis=0`, `skipna=True`|
|`.max(axis=0, skipna=True, numeric_only=False)`|Максимум вдоль оси axis|`axis=0`, `skipna=True`|
|`.sum(axis=0, skipna=True, numeric_only=False)`|Сумма вдоль оси axis|`axis=0`, `skipna=True`|
|`.mean(axis=0, skipna=True, numeric_only=False)`|Среднее арифметическое вдоль оси axis|`axis=0`, `skipna=True`|
|`.median(axis=0, skipna=True, numeric_only=False)`|Медиана вдоль оси axis|`axis=0`, `skipna=True`|
|`.var(axis=0, skipna=True, ddof=1, numeric_only=False)`|Выборочная дисперсия|`axis=0`, `ddof=1`|
|`.std(axis=0, skipna=True, ddof=1, numeric_only=False)`|(Выборочное) стандартное отклонение|`axis=0`, `ddof=1`|
|`.count(axis=0, numeric_only=False)`|Число непропущенных наблюдений по каждому столбцу|`axis=0`|
|`.quantile(q=0.5, axis=0)`|Квантили|`q=0.5` (медиана)|
|`.corr(method='pearson', numeric_only=False)`|Корреляционная матрица|`method='pearson'`|
|`.cov()`|Ковариационная матрица||
|`.mode(axis=0, numeric_only=False)`|Мода (наиболее частое значение)|`axis=0`|
|`.mad(axis=0, skipna=True)`|Среднее абсолютное отклонение|`axis=0`|
|`.sem(axis=0, skipna=True, ddof=1)`|Стандартная ошибка среднего|`axis=0`, `ddof=1`|
|`.skew(axis=0, skipna=True, numeric_only=False)`|Коэффициент асимметрии (skewness)|`axis=0`|
|`.kurt(axis=0, skipna=True, numeric_only=False)`|Коэффициент эксцесса (kurtosis)|`axis=0`|

**Примечание**: `ddof` - delta degrees of freedom (число степеней свободы). `ddof=1` для выборочной статистики, `ddof=0` для генеральной.

### 7.2 Описательные статистики для категориальных переменных

|Метод|Описание|Параметры|
|-|-|-|
|`.value_counts(subset=None, normalize=False, sort=True, ascending=False, dropna=True)`|Частота различных значений в столбцах `subset`|`normalize=False` (доли вместо частот), `dropna=True`|
|`.nunique(axis=0, dropna=True)`|Число уникальных значений|`axis=0`, `dropna=True`|
|`.unique()`|Массив уникальных значений (только для Series)||
|`.mode(axis=0)`|Мода (наиболее частое значение)|`axis=0`|

## 8. Преобразование и очистка данных

### 8.1 Замена значений и преобразование типов

|Метод|Описание|
|-|-|
|`.replace(to_replace, value, inplace=False)`|Замена значений|
|`.map(mapping)`|Применение словаря/функции к Series|
|`.astype(dtype)`|Изменение типа данных|
|`pd.to_numeric(series, errors='raise')`|Преобразование в числовой тип (`errors`: 'raise', 'coerce', 'ignore')|
|`pd.to_datetime(series, format=None, errors='raise')`|Преобразование в datetime|
|`.astype('category')`|Преобразование в категориальный тип|

### 8.2 Агрегация и группировка (groupby)

|Метод|Описание|
|-|-|
|`.groupby(by)`|Группировка по столбцу(ам)|
|`.agg(func)`|Применение функции(й) агрегации|
|`.transform(func)`|Применение функции с сохранением размерности|
|`.filter(func)`|Фильтрация групп по условию|
|`.apply(func)`|Применение произвольной функции к группам|
|`.size()`|Размер каждой группы|
|`.count()`|Количество непропущенных значений в группах|

**Функции агрегации:**

|Функция|Описание|
|-|-|
|`'sum'`|Сумма|
|`'mean'`|Среднее|
|`'median'`|Медиана|
|`'min'`, `'max'`|Минимум, максимум|
|`'std'`, `'var'`|Стандартное отклонение, дисперсия|
|`'count'`|Количество|
|`'first'`, `'last'`|Первое, последнее значение|
|`'nunique'`|Количество уникальных значений|

### 8.3 Объединение датафреймов

|Функция/Метод|Описание|Параметры|
|-|-|-|
|`pd.concat([df1, df2], axis=0)`|Конкатенация (объединение)|`axis=0` (0-вертикально, 1-горизонтально), `ignore_index=False`, `keys=None`|
|`pd.merge(df1, df2, on='key')`|Слияние по ключу (SQL JOIN)|`on`, `left_on`, `right_on`, `how='inner'` ('inner', 'left', 'right', 'outer'), `indicator=False`|
|`.join(other, how='left')`|Слияние по индексу|`how='left'`, `on=None`, `lsuffix=''`, `rsuffix=''`|

**Типы слияния (how):**

|Тип|Описание|SQL аналог|
|-|-|-|
|`'inner'`|Только совпадающие записи|INNER JOIN|
|`'left'`|Все из левого + совпадения|LEFT JOIN|
|`'right'`|Все из правого + совпадения|RIGHT JOIN|
|`'outer'`|Все записи из обоих|FULL OUTER JOIN|
|`'cross'`|Декартово произведение|CROSS JOIN|

### 8.4 Переформирование данных

|Метод|Описание|Направление|
|-|-|-|
|`.pivot(index, columns, values)`|Создание сводной таблицы|Длинный → Широкий|
|`.pivot_table(index, columns, values, aggfunc='mean')`|Сводная таблица с агрегацией|Длинный → Широкий|
|`.melt(id_vars=None, value_vars=None)`|Преобразование в длинный формат|Широкий → Длинный|
|`.stack(level=-1)`|Перенос столбцов в индекс|Широкий → Длинный|
|`.unstack(level=-1)`|Перенос индекса в столбцы|Длинный → Широкий|
|`.transpose()` или `.T`|Транспонирование|Столбцы ↔ Строки|

**Параметры pivot_table:**

|Параметр|Описание|Значение по умолчанию|
|-|-|-|
|`index`|Столбец(ы) для индекса|Обязательный|
|`columns`|Столбец(ы) для столбцов|Обязательный|
|`values`|Столбец(ы) для значений|Все числовые|
|`aggfunc`|Функция агрегации|`'mean'`|
|`fill_value`|Значение для заполнения пропусков|`None`|
|`margins`|Добавить итоговые строки/столбцы|`False`|
|`margins_name`|Имя для итоговых строк/столбцов|`'All'`|

## 9. Вычисление и генерация новых признаков

### 9.1 Применение функций

|Метод|Описание|Применение|
|-|-|-|
|`.apply(func, axis=0)`|Применение функции к строкам/столбцам|DataFrame, Series|
|`.map(func)`|Применение функции к каждому элементу|Series|
|`.applymap(func)` (deprecated)|Применение функции к каждому элементу|DataFrame (использовать `.map()`)|
|`.pipe(func, *args, **kwargs)`|Применение функции к DataFrame в цепочке|DataFrame|

### 9.2 Условные вычисления

|Функция|Описание|
|-|-|
|`np.where(condition, x, y)`|Условный выбор (if-else)|
|`np.select(conditions, choices, default=0)`|Множественный условный выбор|
|`.mask(cond, other=nan)`|Замена значений, где условие True|
|`.where(cond, other=nan)`|Замена значений, где условие False|

### 9.3 Категориальные преобразования

|Функция/Метод|Описание|
|-|-|
|`pd.cut(x, bins, labels=None)`|Биннинг - разбиение на интервалы|
|`pd.qcut(x, q, labels=None)`|Квантильное разбиение|
|`pd.get_dummies(data, prefix=None, prefix_sep='_', drop_first=False, columns=None)`|One-hot encoding (дамми-переменные)|
|`.astype('category')`|Преобразование в категориальный тип|

### 9.4 Кумулятивные операции

|Метод|Описание|
|-|-|
|`.cumsum(axis=0, skipna=True)`|Кумулятивная сумма|
|`.cumprod(axis=0, skipna=True)`|Кумулятивное произведение|
|`.cummin(axis=0, skipna=True)`|Кумулятивный минимум|
|`.cummax(axis=0, skipna=True)`|Кумулятивный максимум|

### 9.5 Скользящие окна

|Метод|Описание|
|-|-|
|`.rolling(window, min_periods=None)`|Скользящее окно|
|`.expanding(min_periods=1)`|Расширяющееся окно|
|`.ewm(span=None, alpha=None)`|Экспоненциально взвешенное окно|

**После создания окна применяются:**

|Метод|Описание|
|-|-|
|`.mean()`|Среднее в окне|
|`.sum()`|Сумма в окне|
|`.std()`|Стандартное отклонение в окне|
|`.var()`|Дисперсия в окне|
|`.min()`, `.max()`|Минимум, максимум в окне|
|`.median()`|Медиана в окне|
|`.count()`|Количество в окне|

### 9.6 Ранжирование и сравнение

|Метод|Описание|
|-|-|
|`.rank(method='average', ascending=True, pct=False)`|Ранжирование значений|
|`.diff(periods=1)`|Разность между элементами|
|`.pct_change(periods=1)`|Процентное изменение|

Параметр `method` для `.rank()`: `'average'`, `'min'`, `'max'`, `'first'`, `'dense'`

### 9.7 Арифметические операции

|Операция|Описание|Метод|
|-|-|-|
|`+`|Сложение|`.add()`|
|`-`|Вычитание|`.sub()` или `.subtract()`|
|`*`|Умножение|`.mul()` или `.multiply()`|
|`/`|Деление|`.div()` или `.divide()`|
|`//`|Целочисленное деление|`.floordiv()`|
|`%`|Остаток от деления|`.mod()`|
|`**`|Возведение в степень|`.pow()`|

## 10. Работа со строками (String methods)

Доступны через `.str` для Series:

|Метод|Описание|
|-|-|
|`.str.lower()`, `.str.upper()`|Преобразование регистра|
|`.str.capitalize()`, `.str.title()`|Капитализация|
|`.str.strip()`, `.str.lstrip()`, `.str.rstrip()`|Удаление пробелов|
|`.str.replace(pat, repl)`|Замена подстрок|
|`.str.contains(pat, case=True, regex=True)`|Проверка на содержание|
|`.str.startswith(pat)`, `.str.endswith(pat)`|Проверка начала/конца|
|`.str.split(pat=' ', n=-1, expand=False)`|Разделение строк|
|`.str.join(sep)`|Объединение строк|
|`.str.extract(pat, expand=True)`|Извлечение с помощью regex|
|`.str.len()`|Длина строки|
|`.str[start:stop]`|Срезы строк|
|`.str.cat(others=None, sep=None)`|Конкатенация строк|
|`.str.findall(pat)`|Найти все вхождения regex|
|`.str.match(pat)`|Проверка соответствия regex|
|`.str.isalpha()`, `.str.isdigit()`, `.str.isalnum()`|Проверка типа символов|
|`.str.isupper()`, `.str.islower()`|Проверка регистра|
|`.str.pad(width, side='left', fillchar=' ')`|Дополнение до ширины|
|`.str.zfill(width)`|Дополнение нулями слева|

## 11. Работа с датами и временем

Доступны через `.dt` для Series с типом datetime:

|Метод/Свойство|Описание|
|-|-|
|`pd.to_datetime(arg, format=None, errors='raise')`|Преобразование в datetime|
|`.dt.year`, `.dt.month`, `.dt.day`|Компоненты даты|
|`.dt.hour`, `.dt.minute`, `.dt.second`|Компоненты времени|
|`.dt.dayofweek`, `.dt.weekday`|День недели (0=Monday)|
|`.dt.day_name()`, `.dt.month_name()`|Название дня/месяца|
|`.dt.dayofyear`|День года (1-366)|
|`.dt.quarter`|Квартал (1-4)|
|`.dt.is_leap_year`|Високосный год|
|`.dt.days_in_month`|Дней в месяце|
|`.dt.date`, `.dt.time`|Дата, время|
|`.dt.strftime(format)`|Форматирование в строку|
|`.dt.normalize()`|Обнуление времени (00:00:00)|
|`pd.date_range(start, end, periods, freq)`|Создание диапазона дат|
|`pd.Timedelta(days=1)`|Временная дельта|
|`pd.DateOffset(months=1)`|Смещение даты|
|`.dt.tz_localize(tz)`|Установка часового пояса|
|`.dt.tz_convert(tz)`|Конвертация часового пояса|

**Частоты (freq) для date_range:**

|Частота|Описание|Частота|Описание|
|-|-|-|-|
|`'D'`|День|`'H'`|Час|
|`'W'`|Неделя|`'T'` или `'min'`|Минута|
|`'M'`|Конец месяца|`'S'`|Секунда|
|`'MS'`|Начало месяца|`'L'` или `'ms'`|Миллисекунда|
|`'Q'`|Конец квартала|`'U'` или `'us'`|Микросекунда|
|`'QS'`|Начало квартала|`'N'`|Наносекунда|
|`'Y'`|Конец года|`'B'`|Рабочий день|
|`'YS'`|Начало года|`'BM'`|Последний рабочий день месяца|

## 12. Базовая визуализация

|Метод|Описание|Основные параметры|
|-|-|-|
|`.plot(kind='line', **kwargs)`|Базовая визуализация|`x`, `y`, `kind`, `title`, `xlabel`, `ylabel`, `grid=False`, `legend=True`, `figsize`, `rot=None`, `logx=False`, `logy=False`, `subplots=False`|
|`.plot.line(x=None, y=None)`|Линейный график|По умолчанию|
|`.plot.bar(x=None, y=None)`|Столбчатая диаграмма|Вертикальная|
|`.plot.barh(x=None, y=None)`|Горизонтальная столбчатая диаграмма||
|`.plot.hist(column=None, bins=10)`|Гистограмма|`bins` (число интервалов)|
|`.plot.box(column=None)`|Ящик с усами||
|`.plot.scatter(x, y, s=None, c=None)`|Диаграмма рассеяния|`s` (размер), `c` (цвет)|
|`.plot.area(x=None, y=None)`|График с областью||
|`.plot.pie(y)`|Круговая диаграмма||
|`.plot.hexbin(x, y, gridsize=100)`|Гексагональный бинплот||
|`.plot.kde()` или `.plot.density()`|График плотности||
|`.hist(column=None, bins=10)`|Альтернативный метод для гистограммы||
|`.boxplot(column=None, by=None)`|Альтернативный метод для ящика с усами||

**Типы графиков (kind):**

|Kind|Описание|
|-|-|
|`'line'`|Линейный график (по умолчанию)|
|`'bar'`|Столбчатая диаграмма|
|`'barh'`|Горизонтальная столбчатая|
|`'hist'`|Гистограмма|
|`'box'`|Ящик с усами|
|`'kde'`, `'density'`|График плотности|
|`'area'`|График с областью|
|`'pie'`|Круговая диаграмма|
|`'scatter'`|Диаграмма рассеяния|
|`'hexbin'`|Гексагональный бинплот|

## 13. Дополнительные полезные методы

|Метод|Описание|Параметры|
|-|-|-|
|`.copy(deep=True)`|Копирование DataFrame|`deep=True` (глубокое), `deep=False` (поверхностное)|
|`.duplicated(subset=None, keep='first')`|Обнаружение дубликатов|`keep`: 'first', 'last', False|
|`.drop_duplicates(subset=None, keep='first', inplace=False)`|Удаление дубликатов|`keep`: 'first', 'last', False|
|`.unique()`|Уникальные значения (Series)|Возвращает массив|
|`.nunique(axis=0, dropna=True)`|Количество уникальных значений||
|`.isin(values)`|Проверка на вхождение|`values`: список, Series, dict|
|`.between(left, right, inclusive='both')`|Проверка на вхождение в диапазон|`inclusive`: 'both', 'neither', 'left', 'right'|
|`.clip(lower=None, upper=None)`|Обрезка значений до диапазона||
|`.abs()`|Абсолютное значение||
|`.round(decimals=0)`|Округление|`decimals`: int или dict|
|`.memory_usage(deep=False)`|Использование памяти|`deep=True` для точного расчета|
|`.empty`|Проверка на пустоту (свойство)||
|`.equals(other)`|Проверка на равенство с другим DataFrame||
|`.idxmin(axis=0)`, `.idxmax(axis=0)`|Индекс минимума/максимума||
|`.argmin(axis=0)`, `.argmax(axis=0)`|Позиция минимума/максимума||
|`.all(axis=0)`, `.any(axis=0)`|Проверка всех/любого на True||

## 14. Оптимизация и производительность

|Метод/Подход|Описание|
|-|-|
|`.astype('category')`|Использование категориального типа для экономии памяти|
|Векторизация|Использование векторизованных операций вместо циклов|
|`.query(expr)`|Более быстрая фильтрация для больших данных|
|`pd.eval(expr)`|Быстрые вычисления для больших выражений|
|Chaining методов|`df.method1().method2().method3()`|
|`.pipe(func, *args, **kwargs)`|Применение функции в цепочке|
|`inplace=True`|Изменение на месте (экономия памяти)|
|Chunking|Чтение больших файлов частями: `pd.read_csv(..., chunksize=10000)`|
|`.info(memory_usage='deep')`|Детальная информация об использовании памяти|

**Советы по оптимизации:**
- Используйте категориальные типы для столбцов с ограниченным набором значений
- Избегайте циклов, используйте векторизованные операции
- Для больших данных читайте файлы частями (chunksize)
- Удаляйте ненужные столбцы как можно раньше
- Используйте `numeric_only=True` в статистических функциях для ускорения

---

## Полезные ссылки

- Официальная документация: https://pandas.pydata.org/docs/
- User Guide: https://pandas.pydata.org/docs/user_guide/index.html
- API Reference: https://pandas.pydata.org/docs/reference/index.html
- Pandas Cheat Sheet: https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf
- Kaggle Datasets для практики: https://www.kaggle.com/datasets