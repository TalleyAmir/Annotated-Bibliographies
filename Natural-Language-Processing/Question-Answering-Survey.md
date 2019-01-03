# Question Answering Survey

A survey on question answering.

### Keywords

question answering, natural language processing, information retrieval, answer retrieval, complex question answering, interactive question answering, reading comprehension

### Overview

Below are various annotated resources pertaining to the natural language processing task of question answering. The works cited below include textbooks, powerpoint presentations, and scientific papers that are related to this problem and proposed solutions for it. This annotated bibliography is intended to cover a broad range of resources on this topic, but it is certainly not exhaustive!

### A Brief History (Chronological)

* Green, Bert F. Jr. Wolf, Alice K. Carol Chomsky, and Kenneth Laughery. 1961. Baseball: an automatic question-answerer. In Papers presented at the May 9-11, 1961, western joint IRE-AIEE-ACM computer conference. ACM, New York, NY, USA, 219-224.

  url:[https://web.stanford.edu/class/linguist289/p219-green.pdf](https://web.stanford.edu/class/linguist289/p219-green.pdf).

  This paper presents one of the earliest attempts to construct a model for general question answering. It is included in this bibliography as more of a 'fun fact' than anything else. This model was used to answer questions exclusively about baseball statistics. The system used syntax parsing and dictionary lookups to respond to questions read in via punch cards. The paper claims that this same method for reasoning extends to data sets beyond the realm of baseball, and the authors of the paper seemed to believe that they had the problem of question answering solved. They essentially argue that if this system cannot handle an input question, there must be some way to rephrase the question so that the desired information can be extracted and returned to the user. However, clearly question answering continues to be so heavily researched today because we are still striving to achieve this kind of performance.

* Bruce Upbin. “IBM Watson Gets Its First Piece of Business in Healthcare”. In: Forbes, 8 February 2013. 

  url:[https://www.forbes.com/sites/bruceupbin/2013/02/08/ibms-watson-gets-its-first-piece-of-business-in-healthcare/#25de6f3a5402](https://www.forbes.com/sites/bruceupbin/2013/02/08/ibms-watson-gets-its-first-piece-of-business-in-healthcare/#25de6f3a5402).

  This Forbes article highlights the increasingly prominent role that question answering systems are playing in society. In particular, the article talks about the ways in which IBM's Watson technology is being applied to the healthcare industry. Though the article offers some notable statistics regarding Watson's reliability and actual use in industry, it does not discuss the legal and ethical issues that are naturally entailed from entrusting a machine with questions whose answers affect human health and mortality. Nonetheless, this source is useful for citing facts about the extent to which IBM Watson is applied to question answering problems in practice.

* Hoa Trang, Dang. “Text REtrieval Conference (TREC) Question Answering Tasks and Evaluation Methods”. In: National Institute of Standards and Technology, April 27, 2007. 

  url:[https://www.yumpu.com/en/document/view/30959076/trec-question-answering-tasks-and-evaluations-document-](https://www.yumpu.com/en/document/view/30959076/trec-question-answering-tasks-and-evaluations-document-). 

  This is a powerpoint presentation that outlines various components of the question answering track in the Text REtrieval Conference (TREC). The presentation gives several examples of challenges posed by the track, and evaluates these challenges in terms of how well previous models performed on them. This is a very useful source for understanding how question answering challenges can be used to standardize evaluations of question answering models. It also provides keen insight on why certain challenges are successful in achieving this goal and why others fail. For more information on TREC and challenges posed at this conference, visit [https://trec.nist.gov/overview.html](https://trec.nist.gov/overview.html).

### Useful Resources (Alphabetical)

* Jurafsky, James H. Martin, Daniel. *Speech and Language Processing*, Third Edition: pp.402-421. 2018. 

  url:[https://web.stanford.edu/~jurafsky/slp3/ed3book.pdf](https://web.stanford.edu/~jurafsky/slp3/ed3book.pdf).

  This is a textbook on natural language processing that consists of various topics ranging from elementary tools, such as regular expressions and edit distance, to important applications in the field, like semantic parsing and machine translation. It provides a chapter on question answering which details a high-level analysis of the task, as well as various approaches to solving it. The chapter discusses broadly the IR-based and knowledge-based question answering paradigms, as well as their uses and general control sequences. The chapter also explains how to evaluate the quality of factoid question answers by explaining various metrics for analyzing such answers. It successfully grounds these technical concepts in context, giving historical examples of how these ideas have been implemented in practice.

* Karl M. Hermann. “Deep Learning for Natural Language Processing: Question Answering”. Google DeepMind. 2017. 

  url:[https://github.com/oxford-cs-deepnlp-2017/lectures/blob/master/Lecture%2011%20-%20Question%20Answering.pdf](https://github.com/oxford-cs-deepnlp-2017/lectures/blob/master/Lecture%2011%20-%20Question%20Answering.pdf).

  This is a power point presentation that introduces the problem of question answering and gives a broad survey of the topic. It provides various applications of the problem and results achieved by various approaches. Several slides give examples of areas in NLP that benefit from the study of question answering, such as semantic parsing and reading comprehension. The diagrams shown are very helpful in understanding flow structure of various quesstion answering systems, such as softmax and reading with attention. Unlike much of the other sources provided in this bibliography, this source discusses topics in visual question answering, as well.

* Klein, Dan. “Natural Language Processing: Question Answering”. University of California, Berkeley. 

  url:[https://people.eecs.berkeley.edu/~klein/cs288/fa14/slides/fa14lecture24-1pp.pdf](https://people.eecs.berkeley.edu/~klein/cs288/fa14/slides/fa14lecture24-1pp.pdf)

  This powerpoint presentation covers a variety of question answering applications and areas of research, such as IBM Watson, TREC, and AskMSR. It also offers some discussion of the results and efficacy of these systems, illustrating their functionality and competency with examples. Though this set of slides gives a broad sampling of question answering applications and gives many illustrious examples from each topic, some components would benefit from further elaboration. Granted, this source is a powerpoint that is intended to be accompanied by a verbal presentation; however, for this reason, some parts of the presentation require external sources to be completely understood (e.g. slides with images explaining the pipeline for Webclopedia's or IBM Watson's architecture). Nevertheless, it is a great jumping-off point.

* Rajpurkar, Pranav. “The Stanford Question Answering Dataset: Background, Challenges, Progress”. April 3, 2017. 

  url:[https://rajpurkar.github.io/mlx/qa-and-squad/](https://rajpurkar.github.io/mlx/qa-and-squad/).

  This is an article about the SQuAD question answering dataset and model. It explains the data collection process, crowdsourcing of questions and answers for the training set, and intuition underlying the model's answer derivation. It covers the motivation, challenges, and results of the dataset, and gives many tangible examples illustrating how the model works and where lies its strengths and weaknesses. This source is authored by the first author on the original SQuAD paper (listed under **Recent Works**) and is a more user-friendly way of demonstrating the advantages and need for the results provided by the SQuAD model.

### Recent Works (Chronological)

* Mohit Iyyer et al. “A Neural Network for Factoid Question Answering Over Paragraphs”. 2014. 

  url:[https://people.cs.umass.edu/~miyyer/pubs/2014_qb_rnn.pdf](https://people.cs.umass.edu/~miyyer/pubs/2014_qb_rnn.pdf).

  This paper describes a method for effectively answering questions from *Quiz Bowl*. The questions in this competition are *pyramidal*, meaning that the first clues given are very difficult, and later clues progressively become more leading. The challenge is to train a neural net to infer the answers to factoid questions based on information that contains very limited key words pertaining to the answer. This forces the net to learn information by modeling the "textual compositionality" of the clues. This paper proposes a model called QANTA -- a question answering neural network with trans-sentential averaging. Though QANTA outperforms IR and BOW models in answering factoid, pyramidal questions, the paper does not evaluate the extent to which QANTA's success relied on the composition of the questions in their data set. The major contribution of this paper is a regression model that incorporates sentence compositionality into its structure.

* Rajpurkar, Pranav. Zhang, Jian. Lopyrev, Konstantin. Liang, Percy. “SQuAD: 100,000+ Questions for Machine Comprehension of Text.” Stanford University, Computer Science Department. 11 October 2016. 

  url:[https://arxiv.org/pdf/1606.05250.pdf](https://arxiv.org/pdf/1606.05250.pdf)

  This paper aims to accomplish effective information retrieval from Wikipedia articles. It does this by developing a large data set comprising many quality questions. The data set is called SQuAD: the Stanford Question Answering Dataset. This data set was a major contribution to the study of question answering. It provides a much larger set of quality questions and answers than any work that precedes it. The model offered by this paper in conjunction with the data set uses both dependency and constituency trees to learn the association between question-answer pairs, and to learn something about the reasoning used to infer the answer from the question. SQuAD gives an immense, curated knowledge base for training question answering systems. It also provides a logistical regression model that, when trained on this vast data source, greatly advanced the level of performance in reading comprehension tasks. Though SQuAD's logistic regression model surpassed baseline performance, it was far from human performance. Nevertheless, it provided a data set that many other papers have since leveraged to tackle question answering.

* Manning, Christopher D. Angeli, Gabor. Nayak, Neha. “Combining Natural Logic and Shallow Reasoning for Question Answering”. 2016. 

  url:[https://nlp.stanford.edu/pubs/angeli2016naturalli.pdf](https://nlp.stanford.edu/pubs/angeli2016naturalli.pdf).

  This paper offers a very syntax-oriented approach to solving question answering. The goal of this paper is to solve open-domain (or broad-domain) question answering by imposing a structure on unstructured data. Specifically, it applies lexical methods and logical reasoning to systematically make sense of unstructured data posed in organic natural language. The model provided in the paper, called NaturalLI, aims to extract from the data includes entailment and meronymy. The model achieves strong results when tested on multiple choice science questions; however, various mistakes are made recurringly by the model. For example, the model does not perform well in cases where complex reasoning is needed in order to identify the correct multiple choice answer. In addition, the model does not do well in classifying, for example, the best hypothesis given some background data, perhaps also because this requires some amount of reasoning beyond the capbility of the model.
  
* Chang, Ming-Wei. Iyyer, Mohit. Yih, Wentau. “Answering Complicated Question Intents Expressed in Decomposed Question Sequences”. 4 November 2016.

  url:[https://arxiv.org/pdf/1611.01242.pdf](https://arxiv.org/pdf/1611.01242.pdf).

  The aim of this paper is to answer complex question sequences that are modeled after naturally occuring conversation so that the model can be implemented in human-interactive applications. The paper presents a dataset of more than 6,000 question and answer sequences called SequentialQA that are formed via crowdworkers that are asked to form questions on tables from Wikipedia. It tests various other models on the dataset and concludes that there are two main points of failure in traditional question answering models. Firstly, these models seem to fail often when later questions reference information presented in previous questions. Second, the models fail when asked to extract information directly from the tables themselves. The paper further elucidates the reasons for previous models' failure on this dataset, and proposes various ways to improve results in future work. This is an excellent source for researching background knowledge on sequential question answering and the state of this research at the time of this paper's publication in 2016.

* Pasupat, Panupong. “WikiTableQuestions: A Complex Real-World Question Answering Dataset”. In: The Stanford Natural Language Processing Group, 2016. 

  url:[https://nlp.stanford.edu/blog/wikitablequestions-a-complex-real-world-question-understanding-dataset/](https://nlp.stanford.edu/blog/wikitablequestions-a-complex-real-world-question-understanding-dataset/).

  This research blog post analyzes a question answering dataset called WikiTableQuestions which asks questions whose answers can be deduced from Wikipedia tables. This post gives animated examples of how, logically, one might systematically try to approach answering a question based on this table structure. It also gives a high level understanding of why such a task is difficult to systematize, or train a computer to do. The post is very accessible, and uses very limited technical jargon. Is it extremely useful in understanding a natural approach to question answering, and how this approach stacks up against other offered in the literature. The post analyzes various other datasets, such as GeoQuery, WikiQA, and QANTA Quiz Bowl, and how these datasets balance the tradeoff between answer breadth and depth.

* Dunn et al. “SearchQA: A New QA Dataset Augmented with Contextfrom a Search Engine”. 11 June 2017. 

  url:[https://arxiv.org/pdf/1704.05179.pdf](https://arxiv.org/pdf/1704.05179.pdf).

  Unlike various other datasets that curate their training data from crowdworkers, SearchQA presents a dataset from existing questions (specifically, questions from the televised game show Jeopardy!). The dataset also includes snippets of text obtained via search over Google's data. In total, the dataset consists of approximately 140,000 question and answer pairs, as well as about 50 snippets from Google each. In this paper, the authors extrapolate from their testing results that this dataset may reveal, with better accuracy, which models are more successful in question answering. The authors tested two baseline methods on the SearchQA dataset and found that there was a large gap between the performances of these two baselines and human performance. This may indicate that SearchQA is a good evaluation metric for question answering. The authors further note that the reason why SearchQA should be used to evaluate question answerers is because of its lack of structure, thereby modeling more realistic applications of question answering.

* Khot et al. “Answering Complex Questions Using Open Information Extraction”. In: ACL 2017, 19 April 2017. 

  url:[http://ai2-website.s3.amazonaws.com/publications/TupleInf_ACL17.pdf](http://ai2-website.s3.amazonaws.com/publications/TupleInf_ACL17.pdf).

  This paper uses open information extraction (Open IE) to answer complex questions. Most Open IE frameworks support factoid question answering, but this paper aims to extend this framework to answer more complex questions. It does this by offering an inference model for reasoning over Open IE. In order to reason over Open IE tuples, this paper uses a type of reasoning similar to that used by the TableILP system introduced by Khashabi et al. in 2016. This paper offers TupleINF, a new inference model that applies ILP optimization techniques to tuples. TupleINF outperforms the ILP model that inspired this approach to a statistically significant extent. Though this model had much success, it also had ample room for improvement. The weighting scheme that was used in the model can inadvertently over-privilege insignificant, low-frequency words, and the method for generating tuples excludes many sentences based on length and structure, thereby limiting the data set. TupleINF describes a model that learns over open information extracted data structures, which makes for more flexible extension of this model to knowledge bases containing information from a variety of domains. It demonstrates how its structure supports extensibility, but its Open IE approach still has several flaws, from issues of scaling to nuanced errors resulting from its tuple generation method.

* McCann et al. “The Natural Language Decathlon: Multitask Learning as Question Answering”. 20 June 2018. 

  url:[https://einstein.ai/static/images/pages/research/decaNLP/decaNLP.pdf](https://einstein.ai/static/images/pages/research/decaNLP/decaNLP.pdf).

  This paper poses a multifaceted natural language processing challenge, as well as a multitask question answering network that aims to solve the set of ten tasks encompassed by the challenge. The aim of this paper is to motivate a model that is not designed to solve any one specific natural language processing task, but can solve multiple tasks using a more general approach. The model presented in the paper is successful on various tasks included in the ten-task challenge, but also performs well on single-task challenges. It achieves this success by avoiding task-specific parameters and modules. In addition to the challenge and the model presented in this paper, the paper also supplies a lot of background information regarding the state of the art in each of the natural language processing tasks in the challenge. It also explains step-by-step how its own model implements novel approaches to general-NLP task solving, such as through alignment and dual-coattention. This is a great resources for understanding how to approach general-NLP task problem solving, and remains an interesting open problem in the area of natural language processing.
