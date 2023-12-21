# Quantifying the Influence of Education Programs on Occupations with Text Embedding and Similarity-based Networks

## Research Aim
Measuring the impact of vocational education that develops a workforce aligned with rapidly changing future industries remains challenging. In contrast to traditional approaches that assess the influence of vocational education based on surveys or achievement tests, analyzing vocational education programs by constructing and examining networks and connecting them to related occupations and skills offers a significant advantage. 

The study utilizes text data on vocational education lectures, occupations, and skills by constructing a similarity-based network based on Sentence-BERT. The study also measures the influence of each vocational education lecture and examines its relationship with employment indices.

## Method
This study utilizes textual descriptions of occupations and job-related skills (n=4037) provided by Skillsfuture Singapore API, along with learning objectives and content of vocational education programs (n=13695). Initially, Sentence-BERT is applied to embed the descriptions of each course, occupation, and skill entity and transform them into 384-dimensional vectors. Subsequently, using cosine similarity with the threshold of 0.6, a bipartite network is constructed, connecting courses to occupations/skills. 

The research suggests course_impact as a novel index to 
![image](https://github.com/lhch9550/Quantify-Course-Impact/assets/74129302/104adb73-dbc6-494e-8627-3d3fe08dcdd9)

The coverage of a course is the number of occupational or skill nodes each course node is connected to, while the k_i represents the degree of course node i within the projected monopartite course network. The defined influence range of each course is then obtained by dividing the course's coverage by the number of connecting lines, yielding the Course Impact Index.

## Result & Discussion

## Citation
[1] E. Pelinescu, Procedia Economics and Finance 22, 184-190 (2015).   
[2] Alabdulkareem et al., Science advances 4 (7), eaao6030 (2018).   
[3] X. Feng and A. Rutherford, Royal Society Open Science 10 (7), 230214 (2023).   
[4] N. Reimers and I. Gurevych, "Sentence-BERT: Sentence Embeddings using Siamese BERT-Networks", arXiv preprint arXiv:1908.10084 (2019).   
[5] C. M. Graham and Y. Lu, Journal of Computer Information Systems 63 (4), 937-949 (2023).	
