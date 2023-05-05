Download Link: https://assignmentchef.com/product/solved-data-mining-assignment-2
<br>



Classification for the Detection of Opinion Spam

<h1>Instructions</h1>

This assignment should be performed by teams of three students. Reports should be handed in by e-mail to <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="6d0c4307430b08080109081f1e2d181843030143">[email protected]</a>

<h1>Introduction</h1>

Consumers increasingly review and rate products online. Examples of review websites are TripAdvisor, Yelp and Rate Your Music. With the growing popularity of these review websites, there comes an increasing potential for monetary gain through opinion spam: fake positive reviews of a company’s product, or fake negative reviews of a competitor’s product. In this assignment, we address the problem of detecting such deceptive opinion spam. Can you tell the fake reviews that have been deliberately written to sound authentic from the genuine truthful reviews?

<h1>The Data</h1>

We analyze fake and genuine hotel reviews that have been collected by Myle Ott and others [1, 2]. The genuine reviews have been collected from several popular online review communities. The fake reviews have been obtained from Mechanical Turk. There are 400 reviews in each of the categories: positive truthful, positive deceptive, negative truthful, negative deceptive. We will focus on the negative reviews and try to discriminate between truthful and deceptive reviews. Hence, the total number of reviews in our data set is 800. For further information, read the articles of Ott et al. [1, 2].

<h1>Analysis</h1>

Ott analyses the data with linear classifiers (naive Bayes and Support Vector Machines with linear kernel). Perhaps the predictive performance can be improved by training a more flexible classifier. We will analyse the data with:

<ol>

 <li>Multinomial naive Bayes (generative linear classifier),</li>

 <li>Regularized logistic regression (discriminative linear classifier),</li>

 <li>Classification trees, (flexible classifier) and</li>

 <li>Random forests (flexible classifier).</li>

</ol>

We use folds 1-4 (640 reviews) for training and hyper-parameter tuning. Fold 5 (160 reviews) is used to estimate the performance of the classifiers that were selected on the training set. Use cross-validation or (for random forests) out-of-bag evaluation to select the values of the hyper-parameters of the algorithms on the training set. You are not required to use the original 4 folds in cross-validation, you may for example create 10 new folds. For naive Bayes, the performance might be improved by applying some form of feature selection (in addition to removing the sparse terms). The other algorithms (trees, regularized logistic regression) have feature selection already built-in. Examples of hyper-parameters are:

<ul>

 <li><em>λ </em>for regularized logistic regression,</li>

 <li>the cost-complexity pruning parameter <em>α </em>(called CP in rpart) for classification trees,</li>

 <li>the number of trees, and the number of randomly selected features for random forests,</li>

 <li>if some feature selection method is used: the number of features for multinomial naive Bayes.</li>

</ul>

You will have to make a number of choices concerning text pre-processing, feature selection, etc. You are not required to try all alternatives, but it is important that you clearly describe (and if at all possible, motivate) the choices you have made, so an interested reader would be able to reproduce your analysis. To measure the performance, use accuracy, precision, recall and the <em>F</em><sub>1 </sub>score.

You should address the following questions:

<ol>

 <li>How does the performance of the generative linear model (multinomialnaive Bayes) compare to the discriminative linear model (regularized logistic regression)?</li>

 <li>Is the random forest able to improve on the performance of the linearclassifiers?</li>

 <li>Does performance improve by adding bigram features, instead of usingjust unigrams?</li>

 <li>What are the five most important terms (features) pointing towards afake review?</li>

 <li>What are the five most important terms (features) pointing towards agenuine review?</li>

</ol>

All in all, the test set should only be used to estimate the performance of eight models: the selected multinomial naive Bayes, logistic regression, classification tree and random forest models, with and without bigram features added. Comparisons of the accuracy of different models should be supported by a statistical test. For the comparison of the other quality measures (precision, recall, <em>F</em><sub>1 </sub>score), a statistical test is not required.

<h1>Software</h1>

You are allowed to use any software to perform the analysis for this assignment, but we can only promise to offer help with the use of R and Python.

<h2>Using R</h2>

We recommend the tm package for pre-processing the text corpus, and creating a document-term matrix. For regularized logistic regression we recommend the package glmnet, in particular its function cv.glmnet for finding good hyper-parameter values through cross-validation. For multinomial naive Bayes, you can use the code provided on the course web page. I didn’t manage to find an R package that implements this model. For classification trees you can use rpart and for random forests the randomForest package. Read the documentation of the packages to learn about their possibilities.

<h2>Using Python</h2>

Python has several libraries for natural language processing, such as NLTK. The library scikit-learn contains implementations of many machine learning algorithms.

<h1>Report</h1>

The report should be written as a paper reporting on an empirical data mining study. This means there should be a proper introduction motivating the problem, a section describing the data that was used in the study, a section describing the setup of the experiments and their results, and a section in which the conclusions are presented. The experiments should be described in sufficient detail, so that the interested reader would be able to reproduce your analysis. For examples, see the papers of Ott et al. [1, 2], and the paper of Zimmermann et al. [3]. There is no page limit for the report.

<h1>References</h1>

<ul>

 <li>Myle Ott, Yejin Choi, Claire Cardie and Jeffrey T. Hancock, <em>Finding deceptive opinion spam by any stretch of the imagination</em>. Proceedings of the 49th meeting of the association for computational linguistics, pp. 309-319, 2011.</li>

 <li>Myle Ott, Claire Cardie and Jeffrey T. Hancock, <em>Negative deceptive opinion spam</em>. Proceedings of NAACL-HLT 2013, pp. 497-501, 2013.</li>

 <li>Thomas Zimmermann, Rahul Premraj and Andreas Zeller, <em>Predicting Defects for Eclipse</em>, Third International Workshop on Predictor Models in Software Engineering, IEEE Computer Society 2007.</li>

</ul>