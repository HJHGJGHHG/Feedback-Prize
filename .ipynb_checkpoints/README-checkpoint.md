# Feedback Prize

## Intro
&emsp;&emsp;Writing is a critical skill for success. However, less than a third of high school seniors are proficient writers, according to the National Assessment of Educational Progress. Unfortunately, low-income, Black, and Hispanic students fare even worse, with less than 15 percent demonstrating writing proficiency. One way to help students improve their writing is via automated feedback tools, which evaluate student writing and provide personalized feedback.

&emsp;&emsp;In this competition, you’ll identify elements in student writing. More specifically, you will automatically segment texts and classify argumentative and rhetorical elements in essays written by 6th-12th grade students. You'll have access to the largest dataset of student writing ever released in order to test your skills in natural language processing, a fast-growing area of data science.

<center><img src="./img/1.png"  style="zoom:30%;" width="100%"/></center>

## Baseline
### 1. Bigbird (fp16)
&emsp;&emsp;超参：
* epochs=5
* bs=32 (4 * gradient_accumulation_steps=8)
* lr=2e-5
* warmup_steps=200
* weight_decay=0.0095
|  step | Overall F1 |Overall Accuracy | CV F1 | Train Loss | Test Loss |
|  :--:  |  :--:   |  :--:   | :--: | :--: | :--: |
| 180 | 0.039594 | 0.721833 | 0 | 1.080800 | 0.556200 |
| 360 | 0.074534 | 0.753678 | 0.002100 | 0.798900 | 0.772938 |
| 540 | 0.140342 | 0.771253 | 0.356300 | 0.720800 | 0.706573 |
| 720 | 0.167472 | 0.770090 | 0.467200 | 0.680300 | 0.693841 |
| 900 | 0.183104 | 0.773777 | 0.479900 | 0.613600 | 0.677752 |
| 1080 | 0.205193 | 0.780050 | 0.516500 | 0.615200 | 0.661614 |
| 1260 | 0.215445 | 0.780060 | 0.521000 | 0.556400 | 0.658024 |
| 1440 | 0.223873 | 0.781856 | 0.522600 | 0.556200 | 0.654915 |
| 1620| 0.229002 | 0.781209 | 0.534200 | 0.524900 | 0.663739 |
| 1800| 0.229772 | 0.783189 | 0.534600 | 0.527800 | 0.661303 |

* Training Time: 04:13:32
* ***LB=***

