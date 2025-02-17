# Определение трендов в видеоиграх

## Описание проекта

У нас есть датафрейм games.csv с данными о название игр, платформе, годе выпуска, жанре игры, продажах в Северной Америке, продажах в Европе, продажах в Японии, продажах в других странах, оценке критиков, оценке пользователей, рейтинге от организации ESRB (англ. Entertainment Software Rating Board).
Нужно выявить определяющие успешность игры закономерности. Наша задача - понять какие факторы влияют на успешность игры за актуальный период в каждом регионе (NA, EU, JP).

Цель исследования:

Определить потенциально прибыльные платформы.
Узнать какие жанры игр наиболее интересны.
Выяснить разницу между пользователями разных регионов (NA, EU, JP).
Ход исследования:

В данном проекте нам нужно сделать обзор данных.
Удалить дубликаты и часть пропусков, заменить часть пропусков на подходящие значения.
Добавить некоторые данные в таблицу.
Провети исследовательский анализ.
Составить портрет пользователя каждого региона.
Проверить несколько гипотез.


## Навыки и инструменты

- **python**
- **pandas**
- **numpy**
- **scipy**
- **matplotlib**

## 

## Общий вывод

Типы данных были заменены в столбцах year_of_release и user_score. 
В year_of_release тип данных float заменили на int, так как год выпуска это целое число.  
В user_score тип данных заменили со строки на численный, так как оценка в данном случае численная.  
  
Строки с пропусками в столбцах name и year_of_release были удалены, так как их невозможно заполнить и они занимают 1.6% от объёма данных.  
Пропуски в critic_score и user_score не стал заполнять, так как в дальнейшем оценка будет браться только за определённый период и сейчас все пропуски заполнять нет смысла. В rating также не стал заполнять пропуски.  
  
Я добавил в датафрейм столбец total_sales, в котором суммируются значения из столбцов na_sales, eu_sales, jp_sales и other_sales.  
  
До 2009 года количество выпущенных за год игр по большей части росло, после чего начало падать. Считаю важными данные с 2013 года.  
  
Исходя из суммарных продаж для всех платформ, выбрал те, которые посчитал успешными и удобными для построения распределения по годам.  
  
По графикам видно, что платформы исчезают примерно через 10 лет после появления, а новые появляются примерно каждые 5-6 лет.  
  
Я взял данные за актуальный период (с 2013 года). Заполнил пропуски в столбце rating строкой 'Nan'.  
За выбранный период (с 2013 года) по продажам лидируют 3DS, PS3, PS4, Wii, X360.  
Продажи всех платформ к 2016 году падают. Потенциально прибыльными в 2017 году можно назвать 3DS, XOne, PS4.   
  
Медианы глобальных продаж почти по всем платформам лежат между 20 и 40. Сильно выбивается PS4, медиана которой больше 80.  
В общем, с увеличением оценки пользователей растёт и количество игр на PS4 с более высоким значением total_sales. 
В случае с оценками критиков зависимость более чёткая. Видно, что они не линейная, но всё-же, по большей части, чем выше оценка, тем выше сборы.  
  
Наибольшее значение медианы суммарных продаж игр имеет жанр 'Shooter'
    
Судя по коэффициенту корреляции от отзывов критиков total_sales зависит куда больше, чем от отзывов пользователей.  
По остальным платформам ситуация примерно такая же. Только на продажи для '3DS' user_score влияет сильнее, чем для других платформ.  
  
Судя по сводным таблицам и круговым диаграммам в EU и NA популярны одни и те же платформы, разница в долях (в EU 'PS4' имеет куда большую долю, чем в NA). В JP популярны другие платформы.  
  
Для NA и EU топы отличаются только пятым жанром. Топ для JP похож на NA, с разницей в одном жанре и последовательности.  
В столбце rating много пропусков. Но по тем строкам, где пропусков в данном столбце нет, можно сделать вывод, что от рейтинга ESRB продажи всё-таки зависят.  
  
По результатам теста есть основания считать, что средние пользовательские рейтинги платформ 'Xbox One' и 'PC' одинаковые.  
По результатам теста есть основания считать, что средние пользовательские рейтинги жанров 'Action' и 'Sports' разные.  
Так как требовалось проверить гипотезы о равенстве и неравенстве, следовательно нулевой гипотезой была гипотеза о равенстве, а альтернативной - о неравенстве.

**Рекомендации:** 
1. В 2017 году потенциально наиболее успешные платформы - '3DS', 'PS4' и 'XOne
2. На продажи игры больше влияет оценка критиков
3. Наиболее прибыльные игры - игры в жанре 'Shooter' и 'Platform' 
4. 
- В NA наибольшую популярность имеют 'PS4' и 'XOne'
- В EU - 'PS4'
- В JP - '3DS'
5. В JP наиболее популярны игры с рейтингом 
