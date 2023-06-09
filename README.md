
![](./images/hh_label.jpg)
# <center> Анализ вакансий из базы данных hh.ru </center>

## Оглавление
1. [Описание проекта](https://github.com/Agent-66/HH-SQL-Analysis/blob/master/README.md#Описание-проекта)
2. [Описание данных](https://github.com/Agent-66/HH-SQL-Analysis/blob/master/README.md#Описание-данных)
3. [Зависимости](https://github.com/Agent-66/HH-SQL-Analysis/blob/master/README.md#Зависимости)
4. [Установка проекта](https://github.com/Agent-66/HH-SQL-Analysis/blob/master/README.md#Установка-проекта)
5. [Использование проекта](https://github.com/Agent-66/HH-SQL-Analysis/blob/master/README.md#Использование-проекта)
6. [Авторы](https://github.com/Agent-66/HH-SQL-Analysis/blob/master/README.md#Авторы)
7. [Выводы](https://github.com/Agent-66/HH-SQL-Analysis/blob/master/README.md#Выводы)

## Описание проекта

**Цель проекта** - анализ данных из базы резюме с сайта поиска вакансий hh.ru к построению модели машинного обучения.

В ходе работы необходимо провести анализ базы данных вакансий для IT-специалистов.

### Какой кейс решаем?

Для кадрового агентства, которое подбирает вакансии для IT-специалистов, необходимо создать модель машинного обучения, которая будет рекомендовать вакансии клиентам агентства, претендующим на позицию Data Scientist. 

В нашем распоряжении база данных с резюме, полученная с сайта поиска вакансий hh.ru.

Нам необходимо понять, что из себя представляют данные и насколько они соответствуют целям проекта. 

На основе полученных данных нужно сделать выводы, за счёт чего получились именно такие цифры, выявить тенденции, сделать прогнозы. Там, где это потребуется, выполнить дополнительные исследования данных.

*В литературе эта часть работы над ML-проектом называется Data Understanding, или анализ данных.*

### Задачи

Проект должен состоять из следующих частей:
1. Знакомство с данными.
2. Предварительный анализ данных.
3. Детальный анализ вакансий.
4. Анализ работодателей.
5. Предметный анализ.
6. Дополнительное исследование данных.

Каждая часть включает блок практических задач, которые необходимо последовательно решить в jupyter-ноутбуках и дать развернутые ответы по проделанной работе.

### Требования к отчету

1. Решение оформляется только в Jupyter Notebook в соответствии с ноутбуком-шаблоном.
2. Каждое задание выполняется в отдельной ячейке, выделенной под задание. Не следует создавать множество ячеек для решения задачи — это создаёт неудобства при проверке.
3. Текст SQL-запросов и код на Python должны быть читаемыми. Соблюдать отступы в SQL-коде.
4. Выводы по каждому этапу оформляются в формате Markdown в отдельной ячейке.
5. Выводы можно дополнительно проиллюстрировать с помощью графиков.
6. Необходимо удалить ячейку с данными соединения перед фиксацией работы в GitHub.

## Описание данных

Все необходимые таблицы находятся в схеме public базы данных project_sql.

База данных содержит следующие таблицы:

**vacancies** - таблица хранит в себе данные по вакансиям.
![](./images/vacancies.png)

**areas** - таблица-справочник, которая хранит код города и его название.
![](./images/areas.png)

**employers** - таблица-справочник со списком работодателей.
![](./images/employers.png)

**industries** - таблица-справочник вариантов сфер деятельности работодателей.
![](./images/industries.png)

**employers_industries** - дополнительная таблица, которая существует для организации связи между работодателями и сферами их деятельности.
![](./images/employers_industries.png)

### Структура проекта

* [images](./images) - папка с изображениями, необходимыми для проекта;
* [headhunter_analysis_sql.ipynb](./headhunter_analysis_sql.ipynb) - jupyter-ноутбук, содержащий основной код проекта и выводы по результатам анализа.

## Зависимости

Python (3.10.6):
* [psycopg2-binary (2.9.5)](https://www.psycopg.org/)

## Установка проекта

```
git clone https://github.com/Agent-66/HH-SQL-Analysis
```

## Использование проекта

Вся информация о работе представлена в jupyter-ноутбуке headhunter_analysis_sql.ipynb.

## Авторы

* [Andrey Razin (Agent-66)](https://github.com/Agent-66)

## Выводы

В процессе работы из базы данных были получены необходимые для анализа выборки. 

На этапе предварительного анализа данных определили число активных вакансий в базе, число зарегистрированных работодателей и сферы их деятельности, регионы размещения вакансий.

В ходе анализа вакансий было исследовано распределение вакансий по регионам, графику работы, типу занятости и опыту работы, выявлены наиболее популярные регионы с вакансиями, вычислена средняя зарплатная вилка по IT-отрасли вцелом.

Анализ работодателей позволил выявить крупнейших работодателей в IT-сфере. Было исследовано распределение вакансий от конкретных работодателей по регионам и выявлены регионы без вакансий. Проанализированы выборки по сферам деятельности работодателей.

На этапе предметного анализа были получены выборки вакансий, подходящих для специалистов по работе с данными. Исследованы ключевые навыки, требуемые от DS-специалистов. Рассчитаны средние заработные платы для DS-специалистов разных уровней.

В ходе дополнительного исследования данных был проведен:
* детальный анализ работодателей масштабы их присутствия на рынке труда;
* изучено распределение вакансий и средней заработной платы по регионам, подготовлены предложения по оптимизации базы данных в части унификации списка имеющихся регионов;
* проведен анализ ключевых навыков, требуемых в IT-сфере вцелом и необходимых для DS-специалистов в частности;
* подготовлены предложения с направлениями дальнейшего исследования вакасий и предобработки преоставленной базы данных.

:arrow_up_small: [к оглавлению](https://github.com/Agent-66/HH-SQL-Analysis/blob/master/README.md#Оглавление)



