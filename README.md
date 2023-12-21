# Quantifying the Influence of Education Programs on Occupations with Text Embedding and Similarity-based Networks

## Research Aim
Measuring the impact of vocational education that develops a workforce aligned with rapidly changing future industries remains challenging. In contrast to traditional approaches that assess the influence of vocational education based on surveys or achievement tests, analyzing vocational education programs by constructing and examining networks and connecting them to related occupations and skills possibly offers a significant advantage. 

The study utilizes text data on vocational education lectures, occupations, and skills by constructing a similarity-based network based on Sentence-BERT. The study also measures the influence of each vocational education lecture and examines its relationship with employment indices.

## Method   
**Quantifying the course impact**   

This study utilizes textual descriptions of occupations and job-related skills (n=4037) provided by Skillsfuture Singapore API, along with learning objectives and content of vocational education programs (n=13695). Initially, Sentence-BERT is applied to embed the descriptions of each course, occupation, and skill entity and transform them into 384-dimensional vectors. Subsequently, using cosine similarity with the threshold of 0.6, a bipartite network is constructed, connecting courses to occupations/skills. 

The research suggests *course* *impact* as a novel index to quantify the influence of individual courses as follows:
![image](https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/104adb73-dbc6-494e-8627-3d3fe08dcdd9)

The coverage of a course is determined by the number of occupational or skill nodes to which each course node is connected. Let *ki* signify the degree of course node *i* within the projected monopartite course network. The Course Impact Index is calculated by dividing the course's coverage by the number of connecting lines. Dividing the number of relevant jobs/skills(which represents the demand of the labor market) by the count of similar courses(which represents the supply from the educational market), we expect the index to offer a balanced assessment of the course's impact within the broader context of the network.   

**Course specificity**   

Sector analysis has been conducted by comparing the proportion of courses with impact indices higher or lower than the overall course impact index median (0.074). A significant difference has been observed in the ratio of above-median to below-median impact indices across various educational sectors. To explore the reasons behind this discrepancy, course specificity has been incorporated into our analysis.

![image](https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/033957c0-11d3-4694-9f76-83d92f894e20)   

The research, focusing on the coverage of specialized jobs/skills by course a, derived course specificity by computing the inverse of *Kc,1*.

![image](https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/cf062b4b-7737-4616-bb58-097d68d57325){: width="300" height="300"){: .center}

## Result & Discussion
The course network, formed by projecting the bipartite network, exhibits a pattern where lectures cluster around educational fields. This suggests that both the text embeddings and the network, constructed based on similarity, effectively preserve the characteristics of vocational education lectures, occupations, and skills.

![image](https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/9a990f76-a4af-4fef-8cda-8e8670c7f6b1)

The proportion of courses with impact indices higher or lower than the overall course impact index median (0.074) was calculated for each field. The results reveal that fields such as Legal, Aerospace, and Engineering have a substantial number of courses with higher impact indices. Conversely, sectors like Leadership & People Management, Education and Training, and Food and Beverages exhibit a prevalence of courses with lower impact indices.

![image](https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/fb660d99-da4f-4fb7-947c-04150f40c9ca)

## Citation
[1] E. Pelinescu, Procedia Economics and Finance 22, 184-190 (2015).   
[2] Alabdulkareem et al., Science advances 4 (7), eaao6030 (2018).   
[3] X. Feng and A. Rutherford, Royal Society Open Science 10 (7), 230214 (2023).   
[4] N. Reimers and I. Gurevych, "Sentence-BERT: Sentence Embeddings using Siamese BERT-Networks", arXiv preprint arXiv:1908.10084 (2019).   
[5] C. M. Graham and Y. Lu, Journal of Computer Information Systems 63 (4), 937-949 (2023).   
[6] C. A. Hidalgo and R. Hausmann, "The building blocks of economic complexity," Proceedings of the national academy of sciences 106 (26), 10570-10575 (2009).

