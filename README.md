# phytaseThesis
Это репозиторий к тезису "Поиск термоацидофильных фитаз в открытых данных микробных сообществ", представленному на Курчатовском геномном форуме в 2024 году.

В папке `plots/` Вы сможете найти иллюстрации к постеру в высоком разрешении.

## Последовательность анализа

1. Сбор метаданных образцов с NCBI taxid 433727 ("hot springs metagenome")
2. Выбор образцов с pH <= 5 и полным метагеномным секвенированием
3. Скачивание последовательностей выбранных образцов с SRA
4. Оценка качества ([FastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/)) и триммирование ([fastp](https://github.com/OpenGene/fastp))
5. Сборка последовательностей ([MEGAHIT](https://github.com/voutcn/megahit))
6. Биннинг полученных контигов и их очистка([MetaWRAP](https://github.com/bxlab/metaWRAP))
7. Поиск кодирующих последовательностей в полученных бинах и их *in silico* трансляция ([Prodigal](https://github.com/hyattpd/Prodigal))
8. Поиск фитаз в предсказанных белках ([HMMER](http://hmmer.org/))
9. Множественное выравнивание фитазы-кандидата на фитазы разных групп([MAFFT](https://mafft.cbrc.jp/alignment/software/)):
     *  по функциональному центру (B-пропеллерные, гистидиновые, цистеиновые и пурпурнокислые фитазы)
     *  по отношению к температуре (мезофилы и термофилы)
10. Построение деревьев по множественным выравниваниям ([IQ-TREE](http://www.iqtree.org/))
11. Визуализация деревьев при помощи пакета [ggtree](https://bioconductor.org/packages/release/bioc/html/ggtree.html) в R
12. Классификация полученных бинов ([GTDB-Tk](https://github.com/Ecogenomics/GTDBTk))

## Список литературы

1. **Microbial phytase: Their sources, production, and role in the enhancement of nutritional aspects of food and feed additives** / *S. Rizwanuddin, V. Kumar, B. Naik, P. Singh, S. Mishra, S. Rustagi, V. Kumar* // Journal of Agriculture and Food Research. — 2023. — Vol. 12. — P. 100559.
2. **Phytases from thermophilic molds: Their production, characteristics and multifarious applications** / *B. Singh, T. Satyanarayana* // Process Biochemistry. — 2011. — Vol. 46, № 7. — P. 1391–1398.
3. **Improved Thermal Stability of a Novel Acidophilic Phytase** / *B.S. Son, S.H. Kim, H.-Y. Sagong, S.R. Lee, E.J. Choi* // Journal of Microbiology and Biotechnology. — 2024. — Vol. 34, № 5. — P. 1119–1125.
4. **Purification and characterization of a novel thermostable phytase from the thermophilic Geobacillus sp. TF16** / *E. Dokuzparmak, Y. Sirin, U. Cakmak, N. Saglam Ertunga* // International Journal of Food Properties. — 2017. — Vol. 20, № 5. — P. 1104–1116.
5. **Shedding light on the composition of extreme microbial dark matter: alternative approaches for culturing extremophiles** / *J. Schultz, F. Modolon, R.S. Peixoto, A.S. Rosado* // Frontiers in Microbiology. — 2023. — Т. 14. — С. 1167718.
