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

#### Гистограмма кластеров по кол-ву разных геномов в кластере

<img width="648" alt="image" src="https://user-images.githubusercontent.com/60758722/173225361-9b88f357-4fa9-4b46-aba6-3307de36b4e1.png">

#### Таблица с информацией по выбранным кластерам

Я выбирала такие кластеры, чтобы и в столбце ```# Speciуs``` и в столбце ```Genes``` было одно и тоже число 5, так как всего мы рассматриваем 5 геномов.
Получается что я буду рассматривать кластеры, в которых находится по одному гену из генома, то есть всего 5 генов.

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
0 | donovani | <img width="359" alt="image" src="https://user-images.githubusercontent.com/60758722/173235549-4c10e256-36b6-48cf-96f9-4cce2f14cdfb.png">
0 | enriettii | <img width="374" alt="image" src="https://user-images.githubusercontent.com/60758722/173235562-9da0487f-6e5e-422a-8e42-77aba07d9a85.png">
0 | infantum JPCM5 | <img width="380" alt="image" src="https://user-images.githubusercontent.com/60758722/173235544-e81df34e-489d-467e-8254-7fdb560ad950.png">
0 | martiniquensis | <img width="389" alt="image" src="https://user-images.githubusercontent.com/60758722/173235578-0f311b55-da1c-437d-9b0c-baf4b6b49832.png">
0 | panamensis | <img width="363" alt="image" src="https://user-images.githubusercontent.com/60758722/173235555-b6f4235f-c7d1-44a9-9870-6b79b0935c27.png">
1 | donovani | <img width="362" alt="image" src="https://user-images.githubusercontent.com/60758722/173235595-90d905bb-fdce-4c9b-8dd1-6ca637c14494.png">
1 | enriettii | <img width="360" alt="image" src="https://user-images.githubusercontent.com/60758722/173235611-4edaf888-c255-481f-83ef-e7fdaf5d69b2.png">
1 | infantum JPCM5 | <img width="366" alt="image" src="https://user-images.githubusercontent.com/60758722/173235585-6c052e27-855a-47ff-bc6c-96f2988321b9.png">
1 | martiniquensis | <img width="370" alt="image" src="https://user-images.githubusercontent.com/60758722/173235618-3d6cf7f4-4af8-49d8-a93c-07158acd853d.png">
1 | panamensis | <img width="360" alt="image" src="https://user-images.githubusercontent.com/60758722/173235604-1273020f-e628-425e-ab98-e822b1051c5d.png">
2 | donovani | <img width="366" alt="image" src="https://user-images.githubusercontent.com/60758722/173235634-c5fdaabc-e089-4556-91d9-b21cd492db81.png">
2 | enriettii | <img width="365" alt="image" src="https://user-images.githubusercontent.com/60758722/173235653-58f6ac3c-f312-43b5-a3cb-56e473d08da0.png">
2 | infantum JPCM5 | <img width="360" alt="image" src="https://user-images.githubusercontent.com/60758722/173235629-7d6878ee-602e-4820-bb55-3a90a8604ec0.png">
2 | martiniquensis | <img width="383" alt="image" src="https://user-images.githubusercontent.com/60758722/173235664-a2777651-0528-4549-97d2-08ca98e7054d.png">
2 | panamensis | <img width="361" alt="image" src="https://user-images.githubusercontent.com/60758722/173235639-4ec2f74f-3161-43c9-b5fa-1bb5ae5a47f4.png">
3 | donovani | <img width="357" alt="image" src="https://user-images.githubusercontent.com/60758722/173235689-d7902ca6-b386-4651-93ca-065d03c1e239.png">
3 | enriettii | <img width="361" alt="image" src="https://user-images.githubusercontent.com/60758722/173235721-10a47396-ca07-4a45-8003-23e20f1d316c.png">
3 | infantum JPCM5 | <img width="353" alt="image" src="https://user-images.githubusercontent.com/60758722/173235681-1db3a67e-4855-4c60-ad97-5874a6f4b081.png">
3 | martiniquensis | <img width="368" alt="image" src="https://user-images.githubusercontent.com/60758722/173235727-452e62ea-6eac-4749-9c32-ca72e610af89.png">
3 | panamensis | <img width="369" alt="image" src="https://user-images.githubusercontent.com/60758722/173235702-197dff51-805a-4533-8382-7646f73ab9f3.png">
4 | donovani | <img width="370" alt="image" src="https://user-images.githubusercontent.com/60758722/173235748-3327e980-3909-4db3-99ef-700c1c6a977a.png">
4 | enriettii | <img width="367" alt="image" src="https://user-images.githubusercontent.com/60758722/173235773-f4c5ea6f-f81f-40c4-b1fd-e2dd822f9890.png">
4 | infantum JPCM5 | <img width="370" alt="image" src="https://user-images.githubusercontent.com/60758722/173235741-3e2ec4a7-9cc9-4e66-b18e-d9b9268ddfe4.png">
4 | martiniquensis | <img width="373" alt="image" src="https://user-images.githubusercontent.com/60758722/173235794-a2704aea-af44-4b92-b431-7f0c496ea52b.png">
4 | panamensis | <img width="359" alt="image" src="https://user-images.githubusercontent.com/60758722/173235753-33c494d1-8590-4615-b630-f51366317c2e.png">
5 | donovani | <img width="353" alt="image" src="https://user-images.githubusercontent.com/60758722/173235874-3d0745b3-903e-48fd-94e7-008c3acb785d.png">
5 | enriettii | <img width="362" alt="image" src="https://user-images.githubusercontent.com/60758722/173235908-a7c38428-f846-4dfa-9ad4-2468a345cb76.png">
5 | infantum JPCM5 | <img width="370" alt="image" src="https://user-images.githubusercontent.com/60758722/173235866-25d07592-7a1c-4a7b-ae11-56eba20b4ffe.png">
5 | martiniquensis | <img width="374" alt="image" src="https://user-images.githubusercontent.com/60758722/173235916-26a05580-b747-4b2f-8a6f-5283eda4f093.png">
5 | panamensis | <img width="385" alt="image" src="https://user-images.githubusercontent.com/60758722/173235898-d2affda0-325e-4d47-8e9e-2b3920ec3d90.png">
6 | donovani | <img width="354" alt="image" src="https://user-images.githubusercontent.com/60758722/173235946-60685aa4-3a6a-4ad1-8742-6d63b5b91c3a.png">
6 | enriettii | <img width="375" alt="image" src="https://user-images.githubusercontent.com/60758722/173235961-7fcd47d1-9035-4560-94f3-17da9a6f2bb5.png">
6 | infantum JPCM5 | <img width="349" alt="image" src="https://user-images.githubusercontent.com/60758722/173235936-438bc6cd-8449-49d7-9d23-6b4d159ccdd6.png">
6 | martiniquensis | <img width="350" alt="image" src="https://user-images.githubusercontent.com/60758722/173235970-660dad02-0667-449e-9703-7a63431409e7.png">
6 | panamensis | <img width="362" alt="image" src="https://user-images.githubusercontent.com/60758722/173235954-4dd03934-8f64-4345-b9e2-b31ec8841fb8.png">
7 | donovani | <img width="372" alt="image" src="https://user-images.githubusercontent.com/60758722/173235985-524c2147-fec8-4f1d-97aa-db53fe11b60f.png">
7 | enriettii | <img width="371" alt="image" src="https://user-images.githubusercontent.com/60758722/173236002-d88a5df9-da0a-4623-a202-b419294fcc4d.png">
7 | infantum JPCM5 | <img width="368" alt="image" src="https://user-images.githubusercontent.com/60758722/173235979-a3197846-9fc7-4bb2-bc0c-23dfb3090c54.png">
7 | martiniquensis | На данный ген не попали Z-DNA
7 | panamensis | <img width="365" alt="image" src="https://user-images.githubusercontent.com/60758722/173235992-6730d77b-b270-4165-a3d4-23f64c61fbd8.png">
8 | donovani | <img width="354" alt="image" src="https://user-images.githubusercontent.com/60758722/173236027-8bf78dcb-e5cf-4ec3-99ae-fd0730da6eb5.png">
8 | enriettii | <img width="383" alt="image" src="https://user-images.githubusercontent.com/60758722/173236048-e880ccf2-fc0b-439a-be64-1f9ebb20a166.png">
8 | infantum JPCM5 | <img width="369" alt="image" src="https://user-images.githubusercontent.com/60758722/173236016-daa53a01-c445-48ad-9815-9662d100365c.png">
8 | martiniquensis | <img width="384" alt="image" src="https://user-images.githubusercontent.com/60758722/173236061-092d5cd2-f68a-4bfb-bc0e-ddb9d3472da2.png">
8 | panamensis | <img width="385" alt="image" src="https://user-images.githubusercontent.com/60758722/173236038-e8630dfb-ffe4-4ddc-80f4-5256ec7cde18.png">
9 | donovani | <img width="362" alt="image" src="https://user-images.githubusercontent.com/60758722/173236078-e9492369-d213-43d7-a75f-6ac69aeb6a79.png">
9 | enriettii | <img width="377" alt="image" src="https://user-images.githubusercontent.com/60758722/173236088-f2f9340e-4313-4c0b-a101-5f683584459e.png">
9 | infantum JPCM5 | <img width="370" alt="image" src="https://user-images.githubusercontent.com/60758722/173236070-995a0bc0-17ca-4b0b-a920-7bcb3d580285.png">
9 | martiniquensis | <img width="361" alt="image" src="https://user-images.githubusercontent.com/60758722/173236095-e484177f-96f0-456f-a8eb-0847a3f82baf.png">
9 | panamensis | <img width="360" alt="image" src="https://user-images.githubusercontent.com/60758722/173236083-e4f7b6fc-d10b-437d-8220-29966ba23814.png">

На каждом рисунке выше отрисован ген из генома, попадающий в соотвествующий кластер. На каждом гене, отрисованы все z-dna с их zh-score. Такая визуализация помогает увидеть где именно находится участок z-dna относительно гена. Каждый ген подписан по следующему принципу: gene + LOCUS(из файла gbff), где LOCUS отвечает за то, к какому геному принадлежит ген. Из визуализации и координат можно заметить, что во многих случаях z-dna попадает на экзон интрон и промоутер, за исключением следующих случаев:
Номер кластера | Название вида | Куда попадает
---|---|---
1 | enriettii | промоутер и интрон
1 | panamensis | промоутер и интрон
3	| panamensis | промоутер и интрон
5	| enriettii | промоутер и интрон
5	| infantum JPCM5 | промоутер и интрон
5	| martiniquensis | промоутер и интрон
5	| panamensis | промоутер и интрон
6	| panamensis | промоутер и интрон
7	| donovani | интрон
7	| enriettii | интрон
7	| martiniquensis	| На данный ген не попали Z-DNA
7	| panamensis | промоутер и интрон
9	| panamensis | промоутер и интрон
