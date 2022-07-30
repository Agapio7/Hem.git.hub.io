

### Minerva Model Solves College Level Math Problems



**Minerva, a language model that achieves strong performance on many quantitative reasoning
tasks.**
* The model is able to process scientific and mathematical questions formulated in natural language,
and generate step-by-step solutions using correct LATEX notation.

* Minerva works on  the PaLM general language models  that are further trained on a high-quality dataset containing scientific and mathematical data. 

![o](https://user-images.githubusercontent.com/91752852/181919135-5661e4a7-1f68-4d8b-b1f1-7428c9a8652d.png)
Example questions from the Joint Entrance Examination Main Math 2020 exam taken each year by almost 2M Indian high-school students intended to study engineering and similar fields (left), and the National Math Exam in Poland (May 2022) taken by approximately 270K high-school students every year (right).

* In particular, started with 8B, 62B,
and 540B parameter pretrained models, and continue training them on our technical content dataset.
![image5](https://user-images.githubusercontent.com/91752852/181919184-541cf740-0905-4dec-a2a3-df6ececa9eeb.png)
Solving a multi-step problem: A question from the MATH dataset and Minerva’s solution. The model writes down a line equation, simplifies it, substitutes a variable, and solves for y.

 * The model achieves state-of-the-art performance on MATH , GSM8k , and a STEM subset of the MMLU Hendrycks et al. (2020) dataset, all of which include math and science questions formulated in natural language

 * To promote quantitative reasoning, Minerva builds on the Pathways Language Model (PaLM), with further training on a 118GB dataset of scientific papers from the arXiv preprint server and web pages that contain mathematical expressions using LaTeX, MathJax, or other mathematical typesetting formats.

![image1](https://user-images.githubusercontent.com/91752852/181919040-f0872b79-49c0-4229-a7bf-34219e9fd084.png)
A dataset for quantitative reasoning: Careful data processing preserves mathematical information, allowing the model to learn mathematics at a higher level.


 * Standard text cleaning procedures often remove symbols and formatting that are essential to the semantic meaning of mathematical expressions. By maintaining this information in the training data, the model learns to converse using standard mathematical notation.


`Minerva also incorporates recent prompting and evaluation techniques such as chain of thought or scratchpad prompting to better solve mathematical questions. Minerva uses majority voting on these sampled solutions(not identical solutions), taking the most common result as the conclusive final answer.`


![image7](https://user-images.githubusercontent.com/91752852/181918892-7daa9d37-a221-4fcc-9d63-0f5d2ef2768a.gif)



## Evaluation on STEM Benchmarks

To test Minerva’s quantitative reasoning abilities the model was evaluated  on STEM benchmarks ranging tough tasks from grade school level problems to graduate level coursework.
 

<h1> MATH: High school math competition level problems</h1>


MMLU-STEM: A subset of the Massive Multitask Language Understanding benchmark focused on STEM, covering topics such as engineering, chemistry, math, and physics at high school and college level.

GSM8k: Grade school level math problems involving basic arithmetic operations that should all be solvable by a talented middle school student.

![image2](https://user-images.githubusercontent.com/91752852/181918942-4a8c59b2-456f-4583-9365-1c7c2a46acc3.png)

Evaluation results on MATH and MMLU-STEM, which include high school and college level questions covering a range of STEM topics.



## Limitations 

* No automatic way of verifying the correctness of the model’s answers. This is in contrast to formal approaches, for which automatic verification is intrinsic. 
* No access to external tools such as a calculator or a Python interpreter. So it is limited in its ability to perform quantitative reasoning tasks that require complicated numerical
calculations. 
* Since the model was trained on a large amount of data, the model has little direct control over the specific capabilities that the model acquired.


Reference 

https://ai.googleblog.com/2022/06minerva-solving-quantitative-reasoning.html 

https://minerva-demo.github.io/#category=Algebra&index=1

https://arxiv.org/pdf/2206.14858.pdf

