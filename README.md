# Геологические данные  
## Описание проекта  
Допустим, мы работаем в добывающей компании «ГлавРосГосНефть». Нужно решить, где бурить новую скважину.  
**Шаги для выбора локации:** 
* В избранном регионе собирают характеристики для скважин: качество нефти и объём её запасов;
* Строят модель для предсказания объёма запасов в новых скважинах;
* Выбирают скважины с самыми высокими оценками значений;
* Определяют регион с максимальной суммарной прибылью отобранных скважин.
* Нам предоставлены пробы нефти в трёх регионах. Характеристики для каждой скважины в регионе уже известны. Построем модель для определения региона, где добыча принесёт наибольшую прибыль. Проанализируем возможную прибыль и риски техникой Bootstrap.  

**Описание данных**

* id — уникальный идентификатор скважины;
* f0, f1, f2 — три признака точек;
* product — объём запасов в скважине (тыс. баррелей).

**Условия задачи:**  

Для обучения модели подходит только линейная регрессия (остальные — недостаточно предсказуемые).
При разведке региона исследуют 500 точек, из которых с помощью машинного обучения выбирают 200 лучших для разработки.
Бюджет на разработку скважин в регионе — 10 млрд рублей. При нынешних ценах один баррель сырья приносит 450 рублей дохода. Доход с каждой единицы продукта составляет 450 тыс. рублей, поскольку объём указан в тысячах баррелей.
После оценки рисков нужно оставить лишь те регионы, в которых вероятность убытков меньше 2.5%. Среди них выбирают регион с наибольшей средней прибылью.  

## Было сделано  
Проведен анализ данных, построена модель машинного обучения(линейная регрессия) для предсказания объема сырья в скважинах. 
Посчитана прибыль и риски в 200 лучших скважинах, вычислен предполагаемый объем сырья. Использована техника `bootstrap`, чтобы найти распределение прибыли. Выбран оптимальный регион для бурения новых скважин.  

## Выводы  
В нашем распоряжении были данные по пробам нефти в трех регионах, в каждом по 10 тыс скважин. 
Необходимо было определить, где бурить новые скважины будет наиболее выгодно. 
Бюджет на одну скважину составляет 50 млн рублей, а необходимый объем для безубыточной добычи нефти - 111 тыс баррелей.  
Мы проанализировали данные и выяснили, что на данный момент средний запас сырья недостаточен для окупаемости разработки скважины. 
Мы построили модель линейной регрессии, которая предсказывала средний запас сырья в каждом регионе. 
Применили технику bootstrap с разделением каждого предсказанного значения прибыли по регионам на 1000 подвыборок.  
Для разработки 200 новых скважин выбран второй регион, так как только там риск убытков менее 2.5%, а именно 1.5%. 
Средняя прибыль там состовляет 456 млн рублей.
