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

Номер кластера | Название вида | product_accession | Имя | Функция гена | Ссылка на источник
---|---|---|---|---|---
0 | donovani | CBZ36062.1 | hypothetical protein, conserved | функционально не охарактеризован | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC524295/
0 | enriettii | KAG5473030.1 | hypothetical protein | определение функции затруднено | https://en.wikipedia.org/wiki/Hypothetical_protein
0 | infantum JPCM5 | CAM69935.1 | conserved hypothetical protein | функционально не охарактеризован | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC524295/
0 | martiniquensis | KAG5472261.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
0 | panamensis | AIO00276.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
1 | donovani | CBZ31255.1 | hypothetical protein, conserved | функционально не охарактеризован | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC524295/
1 | enriettii | KAG5486925.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
1 | infantum JPCM5 | CBZ08318.1 | conserved hypothetical protein | функционально не охарактеризован | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC524295/
1 | martiniquensis | KAG5487692.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
1 | panamensis | AIN95248.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
2 | donovani | CBZ31885.1 | hypothetical protein, conserved | функционально не охарактеризован | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC524295/
2 | enriettii | KAG5485099.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
2 | infantum JPCM5 | CBZ08369.1 | conserved hypothetical protein | функционально не охарактеризован | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC524295/
2 | martiniquensis | KAG5485768.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
2 | panamensis | AIN95850.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
3 | donovani | CBZ33322.1 | serine/threonine protein phosphatase type 5, putative | Играет положительную роль в адипогенезе, регулирует циркадные ритмы, может играть роль в регуляции ионных каналов | https://www.uniprot.org/uniprot/P53042
3 | enriettii | KAG5481624.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
3 | infantum JPCM5 | CAM67068.1  | putative serine/threonine protein phosphatase type 5 | Играет положительную роль в адипогенезе, регулирует циркадные ритмы, может играть роль в регуляции ионных каналов | https://www.uniprot.org/uniprot/P53042
3 | martiniquensis | KAG5480985.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
3 | panamensis | AIN97196.1 | serine/threonine protein phosphatase type 5, putative | Играет положительную роль в адипогенезе, регулирует циркадные ритмы, может играть роль в регуляции ионных каналов | https://www.uniprot.org/uniprot/P53042
4 | donovani | CBZ32552.1 | hypothetical protein, conserved | функционально не охарактеризован | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC524295/
4 | enriettii | KAG5483451.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
4 | infantum JPCM5 | CAM66459.1 | conserved hypothetical protein | функционально не охарактеризован | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC524295/
4 | martiniquensis | KAG5484026.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
4 | panamensis | AIN96482.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
5 | donovani | CBZ31279.1 | hypothetical protein, conserved | функционально не охарактеризован | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC524295/
5 | enriettii | KAG5486948.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
5 | infantum JPCM5 | CAM60013.1 | conserved hypothetical protein | функционально не охарактеризован | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC524295/
5 | martiniquensis | KAG5487716.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
5 | panamensis | AIN95270.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
6 | donovani | CBZ36459.1 | mevalonate kinase, putative | катализирует превращение мевалоната в фосфомевалонат | https://www.sciencedirect.com/topics/neuroscience/mevalonate-kinase
6 | enriettii | KAG5471934.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
6 | infantum JPCM5 | CAM70439.1 | putative mevalonate kinase | катализирует превращение мевалоната в фосфомевалонат | https://www.sciencedirect.com/topics/neuroscience/mevalonate-kinase
6 | martiniquensis | KAG5471283.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
6 | panamensis | AIO00643.1 | mevalonate kinase, putative | катализирует превращение мевалоната в фосфомевалонат | https://www.sciencedirect.com/topics/neuroscience/mevalonate-kinase
7 | donovani | CBZ33319.1 | hypothetical protein, conserved | функционально не охарактеризован | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC524295/
7 | enriettii | KAG5481621.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
7 | infantum JPCM5 | CAM67065.1 | conserved hypothetical protein | функционально не охарактеризован | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC524295/
7 | martiniquensis | KAG5480982.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
7 | panamensis | AIN97193.1 | ARF-like 2-binding protein, putative | активацию ферментов, таких как фосфатидилинозитол (PtdIns) киназы | https://www.nature.com/articles/nrm3117
8 | donovani | CBZ33031.1 | hypothetical protein, conserved | функционально не охарактеризован | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC524295/
8 | enriettii | KAG5482503.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
8 | infantum JPCM5 | CAM66930.1 | conserved hypothetical protein | функционально не охарактеризован | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC524295/
8 | martiniquensis | KAG5481974.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
8 | panamensis | AIN96925.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
9 | donovani | CBZ36064.1 | WD-40 repeat protein | участвуют в росте, клеточном цикле, развитии и вирулентности | https://link.springer.com/article/10.1007/s10930-018-9785-7
9 | enriettii | KAG5473032.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
9 | infantum JPCM5 | CAM69937.1 | WD-40 repeat protein | участвуют в росте, клеточном цикле, развитии и вирулентности | https://link.springer.com/article/10.1007/s10930-018-9785-7
9 | martiniquensis | KAG5472263.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein
9 | panamensis | AIO00278.1 | hypothetical protein | определение функции затруднено| https://en.wikipedia.org/wiki/Hypothetical_protein

 Про расположение Z-DNA и Z-DNA score легче на рисунке показать, который будет представлен ниже.

# Множественное белковое выравнивание

Для каждого выбранного кластера было произведено множественное белоковое выравнивание на сайте https://www.ebi.ac.uk/Tools/msa/clustalo/ . В качестве алгоритма для выравнивания был выбран алгоритм ```ClustalW with character counts```. Файлы с выравниванием можно найти в папке data.

# Визуализация расположения участков Z-DNA для каждого выбранного кластера

Номер кластера | Название вида | Визуализация
---|---|---
0 | donovani | <img width="363" alt="image" src="https://user-images.githubusercontent.com/60758722/173232299-8ed0c4f3-1cbf-447c-86b0-4cb65c2b3299.png">
0 | enriettii | <img width="360" alt="image" src="https://user-images.githubusercontent.com/60758722/173232347-ddea5640-ed4d-4140-8e2a-e16bb20903f5.png">
0 | infantum JPCM5 | <img width="369" alt="image" src="https://user-images.githubusercontent.com/60758722/173232282-70dad52d-81e5-4e92-81ff-5f1a07bd2141.png">
0 | martiniquensis | <img width="360" alt="image" src="https://user-images.githubusercontent.com/60758722/173232358-201065cc-89af-4543-b014-c737f65ef392.png">
0 | panamensis | <img width="367" alt="image" src="https://user-images.githubusercontent.com/60758722/173232336-5ceb7df0-6bbb-419c-b793-c2a03d98ac65.png">
1 | donovani | <img width="352" alt="image" src="https://user-images.githubusercontent.com/60758722/173232464-6763199b-c017-4a4d-8442-97e8d8a50005.png">
1 | enriettii | <img width="361" alt="image" src="https://user-images.githubusercontent.com/60758722/173232499-1ef26f77-7a8d-4f41-9f86-c109a5c70371.png">
1 | infantum JPCM5 | <img width="356" alt="image" src="https://user-images.githubusercontent.com/60758722/173232457-cb3224c6-5461-460b-a827-db8c4d3a93bd.png">
1 | martiniquensis | <img width="346" alt="image" src="https://user-images.githubusercontent.com/60758722/173232513-c7e9f707-e5c5-439f-972b-bfcc2a851f6b.png">
1 | panamensis | <img width="356" alt="image" src="https://user-images.githubusercontent.com/60758722/173232491-6f50e153-69d0-425b-8009-ae29f928c174.png">
2 | donovani | <img width="363" alt="image" src="https://user-images.githubusercontent.com/60758722/173232534-3a50537c-9370-450a-a4bc-71e595438afe.png">
2 | enriettii | <img width="386" alt="image" src="https://user-images.githubusercontent.com/60758722/173232552-dfa1423b-506b-4a9a-82eb-2989774e1fc2.png">
2 | infantum JPCM5 | <img width="361" alt="image" src="https://user-images.githubusercontent.com/60758722/173232523-f573faa9-bc4f-4610-ba58-020551f22dde.png">
2 | martiniquensis | <img width="414" alt="image" src="https://user-images.githubusercontent.com/60758722/173232557-1f0b3c67-caf1-4a96-af23-81f3862109c9.png">
2 | panamensis | <img width="368" alt="image" src="https://user-images.githubusercontent.com/60758722/173232543-a4b20f50-2a24-4cc4-bcac-1225b365e70e.png">
3 | donovani | <img width="358" alt="image" src="https://user-images.githubusercontent.com/60758722/173232633-8826ddd8-632f-4726-892c-da52de374e40.png">
3 | enriettii | <img width="349" alt="image" src="https://user-images.githubusercontent.com/60758722/173232646-c0b29c4f-fd80-451c-a2b0-e8c4eb6784cc.png">
3 | infantum JPCM5 | <img width="355" alt="image" src="https://user-images.githubusercontent.com/60758722/173232629-9c07658a-4e0a-4acb-9b7d-78a6c1cde5cb.png">
3 | martiniquensis | <img width="351" alt="image" src="https://user-images.githubusercontent.com/60758722/173232656-9ce55121-746d-4d7b-a096-fe142fd74fdc.png">
3 | panamensis | <img width="356" alt="image" src="https://user-images.githubusercontent.com/60758722/173232638-ff03d8e2-dc1c-4da0-8d01-1a0cac968050.png">
4 | donovani | <img width="367" alt="image" src="https://user-images.githubusercontent.com/60758722/173232675-bf7e195f-ba6e-4218-9f75-917028dea941.png">
4 | enriettii | <img width="365" alt="image" src="https://user-images.githubusercontent.com/60758722/173232692-5d3f45e1-da26-4073-8981-b7abd4703a0a.png">
4 | infantum JPCM5 | <img width="376" alt="image" src="https://user-images.githubusercontent.com/60758722/173232662-0417bfb6-7b45-4bbc-9d4a-89d649cfcba8.png">
4 | martiniquensis | <img width="372" alt="image" src="https://user-images.githubusercontent.com/60758722/173232700-ca344b3a-8fb2-4f66-b7de-538f9f0eb44b.png">
4 | panamensis | <img width="378" alt="image" src="https://user-images.githubusercontent.com/60758722/173232684-6fa14338-6880-4a0e-815b-518583f8fcec.png">
5 | donovani | <img width="352" alt="image" src="https://user-images.githubusercontent.com/60758722/173232731-c883ea3c-82f4-46c9-ba10-8c9355adfad6.png">
5 | enriettii | <img width="357" alt="image" src="https://user-images.githubusercontent.com/60758722/173232782-7e6d5ec0-4758-487c-85dd-95d659233f99.png">
5 | infantum JPCM5 | <img width="367" alt="image" src="https://user-images.githubusercontent.com/60758722/173232722-4e90d138-6091-489b-a0d4-c78f197d5ead.png">
5 | martiniquensis | <img width="357" alt="image" src="https://user-images.githubusercontent.com/60758722/173232791-309f6559-a2ae-41b6-a767-5a92f37e8d45.png">
5 | panamensis | <img width="349" alt="image" src="https://user-images.githubusercontent.com/60758722/173232770-29517b3b-8a40-470b-b517-3f24b9d40c71.png">
6 | donovani | <img width="349" alt="image" src="https://user-images.githubusercontent.com/60758722/173232804-6887f0da-a0f7-433d-931b-8836e12a8b43.png">
6 | enriettii | <img width="360" alt="image" src="https://user-images.githubusercontent.com/60758722/173232822-cb486585-a025-42af-a14d-5614f9c6a53e.png">
6 | infantum JPCM5 | <img width="351" alt="image" src="https://user-images.githubusercontent.com/60758722/173232799-a083805d-e06d-4284-b2f1-1d03f7dee40a.png">
6 | martiniquensis | <img width="343" alt="image" src="https://user-images.githubusercontent.com/60758722/173232831-d3238211-9334-481e-8c46-0a9a57cc8835.png">
6 | panamensis | <img width="357" alt="image" src="https://user-images.githubusercontent.com/60758722/173232816-6ae41c66-7d0a-4c87-87b7-c36de8515cd7.png">
7 | donovani | <img width="356" alt="image" src="https://user-images.githubusercontent.com/60758722/173232851-55ba9ad0-3f27-4ad9-9a3f-a9b189bf2477.png">
7 | enriettii | <img width="369" alt="image" src="https://user-images.githubusercontent.com/60758722/173232904-e6ba1464-5112-48ee-b63c-707ea63a6dea.png">
7 | infantum JPCM5 | <img width="349" alt="image" src="https://user-images.githubusercontent.com/60758722/173232843-b54c4859-abaf-4ba3-bf50-7de48a6c629e.png">
7 | martiniquensis | На данный ген не попали Z-DNA
7 | panamensis | <img width="345" alt="image" src="https://user-images.githubusercontent.com/60758722/173232898-f8ec2d2b-c73d-4ed3-b041-a39742cf0801.png">
8 | donovani | <img width="359" alt="image" src="https://user-images.githubusercontent.com/60758722/173232943-f71a5ddc-248a-4d8e-9175-e2726561bc86.png">
8 | enriettii | <img width="366" alt="image" src="https://user-images.githubusercontent.com/60758722/173232966-8a6e59c5-5aee-4206-9a63-cc63dcbd177b.png">
8 | infantum JPCM5 | <img width="380" alt="image" src="https://user-images.githubusercontent.com/60758722/173232934-f703f0a7-e128-4aca-8ab5-80d98801ecd5.png">
8 | martiniquensis | <img width="366" alt="image" src="https://user-images.githubusercontent.com/60758722/173232979-b8c6e730-6cdb-441a-aaa2-f3ef708a4d23.png">
8 | panamensis | <img width="367" alt="image" src="https://user-images.githubusercontent.com/60758722/173232956-e198dcd0-6ce5-4233-a103-ea6ff9f6059b.png">
9 | donovani | <img width="365" alt="image" src="https://user-images.githubusercontent.com/60758722/173233023-54f0085e-11fa-4ed0-971a-bfd630a19056.png">
9 | enriettii | <img width="353" alt="image" src="https://user-images.githubusercontent.com/60758722/173233069-f6476a2f-a679-4d65-a6f2-2d01d73feb8b.png">
9 | infantum JPCM5 | <img width="361" alt="image" src="https://user-images.githubusercontent.com/60758722/173233006-da20b71f-04be-4956-843f-582bdcfea362.png">
9 | martiniquensis | <img width="350" alt="image" src="https://user-images.githubusercontent.com/60758722/173233080-d45efc0f-1b6a-497c-8ceb-d97bc4d31329.png">
9 | panamensis | <img width="374" alt="image" src="https://user-images.githubusercontent.com/60758722/173233047-52f209e4-b4d8-493e-9403-2c39d20d5acf.png">
