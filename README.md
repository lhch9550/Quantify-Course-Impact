# Quantifying the Influence of Education Programs on Occupations with Text Embedding and Similarity-based Networks

## Research Aim
Measuring the impact of vocational education that develops a workforce aligned with rapidly changing future industries remains challenging. In contrast to traditional approaches that assess the influence of vocational education based on surveys or achievement tests, analyzing vocational education programs by constructing and examining networks and connecting them to related occupations and skills possibly offers a significant advantage. 

The study utilizes text data on vocational education lectures, occupations, and skills by constructing a similarity-based network based on Sentence-BERT. The study also measures the influence of each vocational education lecture and examines its relationship with employment indices.

## Method   
**Quantifying the course impact from network**   

This study utilizes textual descriptions of occupations and job-related skills (n=4037) provided by Skillsfuture Singapore API, along with learning objectives and content of vocational education programs (n=13695). Initially, Sentence-BERT is applied to embed the descriptions of each course, occupation, and skill entity and transform them into 384-dimensional vectors. Subsequently, using cosine similarity with the threshold of 0.6, a bipartite network is constructed, connecting courses to occupations/skills. 

The research suggests **course** **impact** as a novel index to quantify the influence of individual courses as follows:

<p align="center">
<img src="https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/538d52e4-5067-4eb7-bd93-2c5b64270728" width="60%" height="60%">
</p>

<p align="center">
<img src="https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/669769ab-afff-40bb-a863-a87569cf0b07" width="80%" height="80%">
</p>

The coverage of a course is determined by the number of occupational or skill nodes to which each course node is connected. Let *ki* signify the degree of course node *i* within the projected monopartite course network. For Course Impact Index, dividing the number of relevant jobs/skills(which represents the demand of the labor market) by the count of similar courses(which represents the supply from the educational market), we expect the index to offer a balanced assessment of the course's impact within the broader context of the network.   

**Course specificity**   

Sector analysis has been conducted by comparing the proportion of courses with impact indices higher or lower than the overall course impact index median (0.074). A significant difference has been observed in the ratio of above-median to below-median impact indices across various educational sectors. To explore the reasons behind this discrepancy, course specificity has been incorporated into our analysis.

<p align="center">
<img src="https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/033957c0-11d3-4694-9f76-83d92f894e20" width="80%" height="80%">
</p>

To focus on the coverage of specialized jobs/skills by course a, course specificity was derived by taking the inverse of *Kc,1*.

<p align="center">
<img src="https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/2313be43-9f8a-4bf4-b0ff-77f82bc284e7" width="40%" height="30%">
</p>

**Course impact & the Future Economy**

We conduct regression analysis on the Lecture Impact Index to the Employment Index (Transferability) and Diversity Index in the future labor market. The future Employment Index is based on the number of occupations requiring skills related to the Green Economy, Digital Economy, Care Economy, and the Fourth Industrial Revolution (I4.0 Economy) from 2018 to 2021. To obtain the Employment Index for each course, we sum the Employment Index values of the skill nodes connected to each course node in the course-job/skill bipartite network. 

The Diversity Index is defined as the Shannon entropy for the fields of occupations and skills connected to each lecture node in the education-occupation/skill bipartite network.

## Result & Discussion
The course network, formed by projecting the bipartite network, exhibits a pattern where lectures cluster around educational fields. This suggests that both the text embeddings and the network, constructed based on similarity, effectively preserve the characteristics of vocational education lectures, occupations, and skills.

![image](https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/9a990f76-a4af-4fef-8cda-8e8670c7f6b1)

The proportion of courses with impact indices higher or lower than the overall course impact index median (0.074) was calculated for each field. The results reveal that fields such as Legal, Aerospace, and Engineering have a substantial number of courses with higher impact indices. Conversely, other fields including Leadership & People Management, Education and Training, and Food and Beverages exhibit a prevalence of courses with lower impact indices.

<p align="center">
<img src="https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/fb660d99-da4f-4fb7-947c-04150f40c9ca" width="80%" height="80%">
</p>

## Citation
[1] E. Pelinescu, Procedia Economics and Finance 22, 184-190 (2015).   
[2] Alabdulkareem et al., Science advances 4 (7), eaao6030 (2018).   
[3] X. Feng and A. Rutherford, Royal Society Open Science 10 (7), 230214 (2023).   
[4] N. Reimers and I. Gurevych, "Sentence-BERT: Sentence Embeddings using Siamese BERT-Networks", arXiv preprint arXiv:1908.10084 (2019).   
[5] C. M. Graham and Y. Lu, Journal of Computer Information Systems 63 (4), 937-949 (2023).   
[6] C. A. Hidalgo and R. Hausmann, "The building blocks of economic complexity," Proceedings of the national academy of sciences 106 (26), 10570-10575 (2009).

