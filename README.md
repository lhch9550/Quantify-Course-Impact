# Quantifying the influence of Vocational Education and Training with text embedding and similarity-based networks

## Abract
Assessing the potential influence of Vocational Education and Training (VET) courses on creating job opportunities and nurturing work skills has been considered challenging due to the ambiguity in defining their complex relationships and connections with the local economy. Here, we quantify the potential influence of VET courses and explain it with future economy and specialization by constructing a network of more than 17,000 courses, jobs, and skills in Singapore's SkillsFuture data based on their text similarities captured by a text embedding technique, Sentence Transformer. We find that VET courses associated with Singapore's 4th Industrial Revolution economy demonstrate higher influence than those related to other future economies. The course influence varies greatly across different sectors, attributed to the level of specificity of the skills covered. Lastly, we show a notable concentration of VET supply in certain occupation sectors requiring general skills, underscoring a disproportionate distribution of education supply for the labor market.

## Method   
**Quantifying the course impact from the network**   

This study utilizes textual descriptions of occupations and job-related skills (n=4037) provided by Skillsfuture Singapore API, along with learning objectives and content of vocational education programs (n=13695). Initially, Sentence-BERT is applied to embed the descriptions of each course, occupation, and skill entity and transform them into 384-dimensional vectors. Subsequently, using cosine similarity with the threshold of 0.6, a bipartite network is constructed, connecting courses to occupations/skills. 

The research suggests **course** **impact** as a novel index to quantify the influence of individual courses as follows:

<p align="center">
<img src="https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/538d52e4-5067-4eb7-bd93-2c5b64270728" width="60%" height="60%">
</p>

<p align="center">
<img src="https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/669769ab-afff-40bb-a863-a87569cf0b07" width="80%" height="80%">
</p>

The coverage of a course is determined by the number of occupational or skill nodes to which each course node is connected. Let *k<sub>i</sub>* signify the degree of course node *i* within the projected monopartite course network. As to the newly suggested index, dividing the number of relevant jobs/skills(which represents the demand of the labor market) by the count of similar courses(which represents the supply from the educational market), we expect the index to offer a balanced assessment of the course's impact within the broader context of the network.   

**Course specificity & Proficiency**   

Sector analysis has been conducted by comparing the proportion of courses with impact indices higher or lower than the overall course impact index median (0.074). A significant difference has been observed in the ratio of above-median to below-median impact indices across various educational sectors. To explore the reasons behind this discrepancy, course specificity has been incorporated into our analysis.

<p align="center">
<img src="https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/033957c0-11d3-4694-9f76-83d92f894e20" width="80%" height="80%">
</p>

To focus on the coverage of specialized jobs/skills by course a, course specificity was derived by taking the inverse of *Kc,1*.

<p align="center">
<img src="https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/2313be43-9f8a-4bf4-b0ff-77f82bc284e7" width="40%" height="30%">
</p>

Course proficiency is represented by the Relative Comparative Advance (RCA) value of each course concerning skills with high proficiency. In the original dataset, each skill is assigned a proficiency level ranging from 1 to 6, with an additional classification of "Advanced." Skills within proficiency levels 1 to 3 are categorized as low proficiency, while those beyond are considered high proficiency. A higher proficiency index for a course or sector indicates a stronger association with a greater number of high-proficiency skills.

<p align="left">
<img src="https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/2adf444a-d4e6-4962-bd5b-fd522d89c886" width="50%" height="40%">
</p>

**Course impact & the Future Economy**

We conduct regression analysis on the Lecture Impact Index to the Employment Index (Transferability) and Diversity Index in the future labor market. The future Employment Index is based on the number of occupations requiring skills related to the Green Economy, Digital Economy, Care Economy, and the Fourth Industrial Revolution (I4.0 Economy) from 2018 to 2021. To obtain the Employment Index for each course, we sum the Employment Index values of the skill nodes connected to each course node in the course-job/skill bipartite network. The Diversity Index is defined as the Shannon entropy for the categories of jobs and skills connected to each course node in the bipartite network.

## Result & Discussion
The course network, projected from the bipartite network, exhibits a pattern where lectures cluster around educational fields. This suggests that both the text embeddings and the network, constructed based on similarity, effectively preserve the characteristics of vocational education lectures, occupations, and skills.

![image](https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/9a990f76-a4af-4fef-8cda-8e8670c7f6b1)

The proportion of courses with impact indices higher or lower than the overall course impact index median (0.074) was calculated for each field. The results reveal that some sectors such as Legal, Aerospace, and Engineering have a substantial number of courses with higher impact indices. Conversely, other sectors including Leadership & People Management, Education and Training, and Food and Beverages exhibit a prevalence of courses with lower impact indices.


<p align="left">
<img src="https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/fb660d99-da4f-4fb7-947c-04150f40c9ca" width="60%" height="60%">
</p>


It is essential to recognize that increased course specificity does not automatically indicate a correlation with skills requiring advanced proficiency. Our examination, comparing course specificity and proficiency, shows that sectors with heightened specificity often align with lower proficiency levels. This suggests that courses focused on relatively niche occupations and skill sets are better suited for employees aiming to enhance their lower skill levels, particularly those in junior positions.


<p align="left">
<img src="https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/36997a8e-f9ea-43c6-9bc6-d33c998063e9" width="100%" height="100%">
</p>

In our concluding analysis, we performed regression analysis on the Course Impact Index, taking into account employment indices in four economies and diversity indices, resulting in an R<sup>2</sup> of 0.360 and an adjusted R<sup>2</sup> of 0.336. The findings reveal two key insights: 1) a higher Fourth Industrial Revolution employment index correlates with an elevated Course Impact Index, and 2) a lower level of job/skill diversity is related to a higher Course Impact Index. 

It is crucial to note that the Course Impact Index is significantly influenced only by the employment index related to the Fourth Industrial Revolution (β<sub>i4.0</sub> = 0.2024***) or Industry 4.0 economy. This highlights the substantial impact exerted by courses aligned with Industry 4.0 within Singapore's vocational educational space, underscoring the imperative for policy attention. To pinpoint priority course sectors linked to Industry 4.0, we calculated the percentage for each sector by dividing the average number of courses with Industry 4.0 transferability values by the average number of total courses, taking into account only job nodes with industry attributes in the computation. Sectors such as 'Biopharmaceutical manufacturing', 'Public transport', and 'Energy and chemicals' exhibit notably high percentages, while sectors like 'Arts and entertainment' and 'Early childhood care and education' show lower percentages. This suggests that sectors with higher percentages merit increased attention and potentially more investment. Finally, it is noteworthy that both the regression coefficients for job diversity and skill diversity are negative (β<sub>job</sub> = -0.0792**, β<sub>skill</sub> = -0.3572***), implying that courses need to be tailored to specific jobs or skill sets to maximize their impact.

<p align="center">
<img src="https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/36a9a398-ee21-4f9f-a09b-6b4fb6b898ea" width="60%" height="60%">
</p>

## Citation
[1] E. Pelinescu, Procedia Economics and Finance 22, 184-190 (2015).   
[2] Alabdulkareem et al., Science advances 4 (7), eaao6030 (2018).   
[3] X. Feng and A. Rutherford, Royal Society Open Science 10 (7), 230214 (2023).   
[4] N. Reimers and I. Gurevych, "Sentence-BERT: Sentence Embeddings using Siamese BERT-Networks", arXiv preprint arXiv:1908.10084 (2019).   
[5] C. M. Graham and Y. Lu, Journal of Computer Information Systems 63 (4), 937-949 (2023).   
[6] C. A. Hidalgo and R. Hausmann, "The building blocks of economic complexity," Proceedings of the national academy of sciences 106 (26), 10570-10575 (2009).

