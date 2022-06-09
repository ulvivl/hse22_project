# hse22_project

---
# Ссылки
1. [Условие](https://docs.google.com/document/d/1kU0Q6192Wc4tE080A2ZqZUFkjX7Ls_OVvc2gIDuKYx0/edit#)
2. [Colab с кодом](https://colab.research.google.com/drive/1Q11wzyHAOGKgjaSAz116XPAKo8KAybvd?usp=sharing)

---
# Выбранные геномы:

Вид | Уровень сборки | GC% | Название в colab
---|---|---|---
Leishmania donovani | Chromosome | 59,1146 | GCA_00022713
Leishmania enriettii | Chromosome | 59,5865 | GCA_017916305
Leishmania infantum JPCM5 | Chromosome | 59,5663 | GCA_000002875
Leishmania martiniquensis | Chromosome | 59,8521 | GCA_017916325
Leishmania panamensis |  Chromosome | 57,3879 | GCA_000755165

---
# Анализ аннотированных генов

Поскольку я работала с эукариотами, то в таблице ниже представлены число генов, длина генома, длина участков с экзонами, доля покрытия экзонами.

Название вида | Число генов |	Длина генома | Длина участков с экзонами |	Доля покрытия экзонами
---|---|---|---|---
donovani	| 8195	| 32444968	| 14824824	| 45.7
enriettii| 8353	| 33318864	| 15840130	| 47.5
infantum JPCM5 	| 8383	| 32122061	| 15607169	| 48.6
martiniquensis	| 7967	| 32413670	| 14791807	| 45.6
panamensis	| 8048	| 30688794	| 14547601	| 47.4

---
# Предсказание участков Z-DNA

В данном пункте было произведено предсказание участков Z-DNA с помощью программы zhunt. Далее были отобраны только те участки Z-DNA, у которых zh-score больше 500. По полученным данным были посчитаны некоторые показатели, Ниже представлены результаты для каждого генома.

Название вида | Количество предсказанных Z-DNA | Количество участков с zh-score > 500 |	Общая длина участков
---|---|---|---
donovani |	283432 |	9151 |	99396
enriettii |	263205 |	8728 |	94900 
infantum JPCM5 |	277951 |	9051 |	98310 
martiniquensis |	241723 |	6741 |	72132 
panamensis |	268611 |	5617 |	60450 




