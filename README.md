# hse22_project

---
# Ссылки
1. [Условие](https://docs.google.com/document/d/1kU0Q6192Wc4tE080A2ZqZUFkjX7Ls_OVvc2gIDuKYx0/edit#)
2. [Colab с кодом](https://colab.research.google.com/drive/1Q11wzyHAOGKgjaSAz116XPAKo8KAybvd?usp=sharing)

---
# Выбранные геномы

Вид | Уровень сборки | GC% | Название в colab
---|---|---|---
Leishmania donovani | Chromosome | 59,1146 | GCA_00022713
Leishmania enriettii | Chromosome | 59,5865 | GCA_017916305
Leishmania infantum JPCM5 | Chromosome | 59,5663 | GCA_000002875
Leishmania martiniquensis | Chromosome | 59,8521 | GCA_017916325
Leishmania panamensis |  Chromosome | 57,3879 | GCA_000755165

---
# Анализируем аннотированные гены

Поскольку я работала с эукариотами, то в таблице ниже представлены число генов, длина генома, длина участков с экзонами, доля покрытия экзонами.

Название вида | Число генов |	Длина генома | Длина участков с экзонами |	Доля покрытия экзонами
---|---|---|---|---
donovani	| 8195	| 32444968	| 14824824	| 45.7
enriettii| 8353	| 33318864	| 15840130	| 47.5
infantum JPCM5 	| 8383	| 32122061	| 15607169	| 48.6
martiniquensis	| 7967	| 32413670	| 14791807	| 45.6
panamensis	| 8048	| 30688794	| 14547601	| 47.4

---
# Предсказываем участки Z-DNA

В данном пункте было произведено предсказание участков Z-DNA с помощью программы zhunt. Далее были отобраны только те участки Z-DNA, у которых zh-score больше 500. По полученным данным были посчитаны некоторые показатели. Ниже представлены результаты для каждого генома.

Название вида | Количество предсказанных Z-DNA | Количество участков с zh-score > 500 |	Общая длина участков
---|---|---|---
donovani |	283432 |	9151 |	99396
enriettii |	263205 |	8728 |	94900 
infantum JPCM5 |	277951 |	9051 |	98310 
martiniquensis |	241723 |	6741 |	72132 
panamensis |	268611 |	5617 |	60450

#### Гистограммы распределений

Название вида | Гистограмма
---|---
donovani | ![](https://github.com/ulvivl/hse22_project/blob/main/img/GCA_00022713.png)
enriettii | ![](https://github.com/ulvivl/hse22_project/blob/main/img/GCA_017916305.png)
infantum JPCM5 | ![](https://github.com/ulvivl/hse22_project/blob/main/img/GCA_000002875.png)
martiniquensis | ![](https://github.com/ulvivl/hse22_project/blob/main/img/GCA_017916325.png)
panamensis | ![](https://github.com/ulvivl/hse22_project/blob/main/img/GCA_000755165.png)

# Ассоциируем предсказанные участки Z-DNA с промотерами генов

#### Визуализация генов и предсказанных участков Z-DNA с помощью GraphicFeature, GraphicRecord
На картинках ниже изображено по одной Z-DNA, находящейся на промотере гена для 3 генов из генома 
Название вида | Визуализация
---|---
donovani | ![](https://github.com/ulvivl/hse22_project/blob/main/img/GCA_00022713_4.png)
enriettii | ![](https://github.com/ulvivl/hse22_project/blob/main/img/GCA_017916305_4.png)
infantum JPCM5 | ![](https://github.com/ulvivl/hse22_project/blob/main/img/GCA_000002875_4.png)
martiniquensis | ![](https://github.com/ulvivl/hse22_project/blob/main/img/GCA_017916325_4.png)
panamensis | ![](https://github.com/ulvivl/hse22_project/blob/main/img/GCA_000755165_4.png)

#### Визуализация генов и предсказанных участков Z-DNA с помощью IGV

Название вида | Визуализация
---|---
donovani | ![](https://github.com/ulvivl/hse22_project/blob/main/img/GCA_00022713_3.png)
enriettii | ![](https://github.com/ulvivl/hse22_project/blob/main/img/GCA_017916305_3.png)
infantum JPCM5 | ![](https://github.com/ulvivl/hse22_project/blob/main/img/GCA_000002875_3.png)
martiniquensis | ![](https://github.com/ulvivl/hse22_project/blob/main/img/GCA_017916325_3.png)
panamensis | ![](https://github.com/ulvivl/hse22_project/blob/main/img/GCA_000755165_3.png)

#  Определяем гомологичные связи между белками выбранных геномов

Данный этап был выполнен в jupyter notebook, находящийся в папке src, так как там он выполнялся гораздо быстрее, чем в colab.

#### Информация по полученным гомологичным кластерам
Общее число кластеров: 8114

Гистограмма кластеров по кол-ву разных геномов в кластере

<img width="648" alt="image" src="https://user-images.githubusercontent.com/60758722/173225361-9b88f357-4fa9-4b46-aba6-3307de36b4e1.png">

#### Таблица с информацией по выбранным кластерам

Я выбирала такие кластеры, чтобы и в столбце ```# Speciуs``` и в столбце ```Genes``` было одно и тоже число 5, так как всего мы рассматриваем 5 геномов.
Получается что я буду рассматривать кластеры, в которых находится по одному гену из генома.

Номер кластера | Название вида | Название гена | Функция гена
---|---|---|---
0 | donovani | CBZ36062.1 | hypothetical protein, conserved
0 | enriettii | KAG5473030.1 | hypothetical protein
0 | infantum JPCM5 | CAM69935.1 | conserved hypothetical protein
0 | martiniquensis | KAG5472261.1 | hypothetical protein
0 | panamensis | AIO00276.1 | hypothetical protein
1 | donovani | CBZ31255.1 | hypothetical protein, conserved
1 | enriettii | KAG5486925.1 | hypothetical protein
1 | infantum JPCM5 | CBZ08318.1 | conserved hypothetical protein
1 | martiniquensis | KAG5487692.1 | hypothetical protein
1 | panamensis | AIN95248.1 | hypothetical protein
2 | donovani | CBZ31885.1 | hypothetical protein, conserved
2 | enriettii | KAG5485099.1 | hypothetical protein
2 | infantum JPCM5 | CBZ08369.1 | conserved hypothetical protein
2 | martiniquensis | KAG5485768.1 | hypothetical protein
2 | panamensis | AIN95850.1 | hypothetical protein
3 | donovani | CBZ33322.1 | serine/threonine protein phosphatase type 5, putative
3 | enriettii | KAG5481624.1 | hypothetical protein
3 | infantum JPCM5 | CAM67068.1  | putative serine/threonine protein phosphatase type 5
3 | martiniquensis | KAG5480985.1 | hypothetical protein
3 | panamensis | AIN97196.1 | serine/threonine protein phosphatase type 5, putative
4 | donovani | CBZ32552.1 | hypothetical protein, conserved
4 | enriettii | KAG5483451.1 | hypothetical protein
4 | infantum JPCM5 | CAM66459.1 | conserved hypothetical protein
4 | martiniquensis | KAG5484026.1 | hypothetical protein
4 | panamensis | AIN96482.1 | hypothetical protein
5 | donovani | CBZ31279.1 | hypothetical protein, conserved
5 | enriettii | KAG5486948.1 | hypothetical protein
5 | infantum JPCM5 | CAM60013.1 | conserved hypothetical protein
5 | martiniquensis | KAG5487716.1 | hypothetical protein
5 | panamensis | AIN95270.1 | hypothetical protein
6 | donovani | CBZ36459.1 | mevalonate kinase, putative
6 | enriettii | KAG5471934.1 | hypothetical protein
6 | infantum JPCM5 | CAM70439.1 | putative mevalonate kinase
6 | martiniquensis | KAG5471283.1 | hypothetical protein
6 | panamensis | AIO00643.1 | mevalonate kinase, putative
7 | donovani | CBZ33319.1 | hypothetical protein, conserved
7 | enriettii | KAG5481621.1 | hypothetical protein
7 | infantum JPCM5 | CAM67065.1 | conserved hypothetical protein
7 | martiniquensis | KAG5480982.1 | hypothetical protein
7 | panamensis | AIN97193.1 | ARF-like 2-binding protein, putative
8 | donovani | CBZ33031.1 | hypothetical protein, conserved
8 | enriettii | KAG5482503.1 | hypothetical protein
8 | infantum JPCM5 | CAM66930.1 | conserved hypothetical protein
8 | martiniquensis | KAG5481974.1 | hypothetical protein
8 | panamensis | AIN96925.1 | hypothetical protein
9 | donovani | CBZ36064.1 | WD-40 repeat protein
9 | enriettii | KAG5473032.1 | hypothetical protein
9 | infantum JPCM5 | CAM69937.1 | WD-40 repeat protein
9 | martiniquensis | KAG5472263.1 | hypothetical protein
9 | panamensis | AIO00278.1 | hypothetical protein


Что еще нужно
(Информация по полученным гомологичным кластерам (сколько всего кластеров + гистограмма кластеров по кол-ву разных геномов в кластере - 5, 4, 3, 2)
Таблица с информацией по выбранным кластерам (сколько генов в кластере, функция этих генов, расположение Z-DNA относительно этих генов, Z-DNA score) - не более 10 шт
Множественное белковое выравнивание для каждого выбранного кластера
Визуализация расположения участков Z-DNA для каждого выбранного кластера
)
