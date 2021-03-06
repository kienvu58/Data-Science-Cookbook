> Written with [StackEdit](https://stackedit.io/).

# Overfitting Notes
![](https://raw.githubusercontent.com/rafjaa/curso-mineracao-de-dados-aplicada/master/img/kernel_overfitting/meme1.jpeg)

The following paragraph comes from:

- [Whty Aren't My Results As Good As I Thought? You're Probably Overfitting](https://machinelearningmastery.com/arent-results-good-thought-youre-probably-overfitting/)

## Why is Overfitting a Problem?

The aim of most machine learning algorithms is to find a mapping from the signal in the data, the important values, to an output. Noise interferes with the establishment of this mapping.

The practical outcome of overfitting is that a classifier which appears to perform well on its training data may perform poorly, possibly very badly, on new data from the same problem. *The signal in the data tends to be pretty much the same from dataset to dataset, but the noise can be very different.*

If a classifier fits the noise as well as the signal, it will not be able to separate signal from noise on new data. And the aim of developing most classifiers is to have them generalise to new data in a predictable way.

> A model that has been overfit will generally have poor predictive performance, as it can exaggerate minor fluctuations in the data

— Overfitting,  [Wikipedia](http://en.wikipedia.org/wiki/Overfitting).

The following notes comes from:

- [What to do with "small" data?](https://medium.com/rants-on-machine-learning/what-to-do-with-small-data-d253254d1a89)

### **_How large datasets help in building better Machine Learning models?_**

Before we jump to how more data improves model performance, we need to understand  **Bias** and  **Variance**.

**Bias:**  Let us consider a data set which has a quadratic relationship between dependent and independent variables. However, we don't know the true relationship and approximate it as linear. In such a case, we will observe a significant difference between our prediction and actual observed data.  This difference between observed value and the predicted value is called  **Bias**.Such models are said to have less power and represent underfitting.

**Variance:** In the same example, if we approximate the relationship as cubic or any higher powers, we have a case of high variance. Variance is defined as the difference in performance on the training set vs on the test set. The major issue with high variance is the model fits the training data really well but it does not generalize well on out of training datasets. This is one of the major reasons validation and test set are very important in the model building process.

Nex paragraph reference:

[breaking-the-curse-of-small-datasets-in-machine-learning-part-1](https://towardsdatascience.com/breaking-the-curse-of-small-datasets-in-machine-learning-part-1-36f28b0c044d)

### **_How large datasets help in building better Machine Learning models?_**

Before we jump to how more data improves model performance, we need to understand  **Bias** and  **Variance**.

**Bias:**  Let us consider a data set which has a quadratic relationship between dependent and independent variables. However, we don't know the true relationship and approximate it as linear. In such a case, we will observe a significant difference between our prediction and actual observed data.  This difference between observed value and the predicted value is called  **Bias**.Such models are said to have less power and represent underfitting.

**Variance:** In the same example, if we approximate the relationship as cubic or any higher powers, we have a case of high variance. Variance is defined as the difference in performance on the training set vs on the test set. The major issue with high variance is the model fits the training data really well but it does not generalize well on out of training datasets. This is one of the major reasons validation and test set are very important in the model building process.

![](https://cdn-images-1.medium.com/max/720/1*dUR71DbSGdBBa3jKzCvfUA.png)

Figure 4: Bias vs Variance ([Source](https://www.coursera.org/learn/machine-learning))

> We generally want to minimize both bias and variance i.e build a model which not only fits the training data well but also generalizes well on test/validation data. There are a lot of techniques to achieve this but training with more data is one of the best ways of achieving this. Lets understand this using the figure below:

![](https://cdn-images-1.medium.com/max/1080/1*h8ExMrGhos6vUgZSvbZAwA.png)

Figure 5: Large data results in better generalization([Source](https://www.microsoft.com/en-us/research/people/cmbishop/?from=http%3A%2F%2Fresearch.microsoft.com%2Fen-us%2Fum%2Fpeople%2Fcmbishop%2Fprml%2Fwebfigs.htm))

Let’s say we have a data distribution which is similar to a sinusoidal wave.  _Fig(5a)_  depicts that multiple models are equally good in fitting the data point. A lot of those models overfit and do not generalize well on the whole dataset. As we increase data,  _Fig(5b)_  illustrates a reduction in the number of models which can fit the data. As we further increase the number of data points, we successfully capture the true distribution of the data as shown in  _Fig(5c)_. This example helps us clearly understand how more data helps the model uncover the true relationship. Next, we will try to understand this phenomenon for some of the Machine learning algorithms and figure out how the model parameters get impacted by the size of the data.

**_(a) Linear Regression:_** In linear regression, we assume a linear relationship between the predictor variables(features) and dependent variables(target) and the relationship is formulated as:
  
![](https://cdn-images-1.medium.com/max/720/1*3gciRARCGv8F2RGyaVH9Sg.jpeg)

where  **_y_**  is the dependent variable and  **_x(i)’s_**  are independent variables.  **_β(i)’s_**are the true coefficients and ϵ is the error not explained by the model. For a univariate case, estimated coefficients based on the observed data are given by:

![](https://cdn-images-1.medium.com/max/720/1*Q_xJN2F5kJPhdlBEaHooSQ.png)

![](https://cdn-images-1.medium.com/max/720/1*7YHiHbj9IugmNO7H-1YI_A.png)

Above equations give us the point estimate of the slope and intercept terms but there is always some uncertainty associated with these estimates which can be quantified by the variance equations:

![](https://cdn-images-1.medium.com/max/720/1*uT-oeRSao0vqwVmAplRvRQ.png)

![](https://cdn-images-1.medium.com/max/720/1*N11JtDyI16ZJ_ywS70xkrA.png)
![](https://cdn-images-1.medium.com/max/720/1*N11JtDyI16ZJ_ywS70xkrA.png)

## Small Data problems

Problems of small-data are numerous, but mainly revolve around high variance:

-   **Over-fitting**  becomes much harder to avoid
-   You don’t only over-fit to your training data, but sometimes you over-fit to your validation set as well.
-   **Outliers**  become much more dangerous.
-   Noise in general becomes a real issue, be it in your target variable or in some of the features.

## Solutions for small data

**Stick to simple models**

More precisely: stick to a limited set of hypotheses. One way to look at predictive modeling is as a search problem. From an initial set of possible models, which is the most appropriate model to fit our data? In a way, each data point we use for fitting down-votes all models that make it unlikely, or up-vote models that agree with it. When you have heaps of data, you can afford to explore huge sets of models/hypotheses effectively and end up with one that is suitable. When you don’t have so many data points to begin with, you need to start from a fairly small set of possible hypotheses (e.g. the set of all linear models with 3 non-zero weights, the set of decision trees with depth <= 4, the set of histograms with 10 equally-spaced bins). This means that you rule out complex hypotheses like those that deal with non-linearity or feature interactions. This also means that you can’t afford to fit models with too many degrees of freedom (too many weights or parameters). Whenever appropriate, use strong assumptions (e.g. no negative weights, no interaction between features, specific distributions, etc.) to restrict the space of possible hypotheses.

**Pool data when possible**

Are you building a personalized spam filter? Try building it on top of a universal model trained for all users. Are you modeling GDP for a specific country? Try fitting your models on GDP for all countries for which you can get data, maybe using importance sampling to emphasize the country you’re interested in. Are you trying to predict the eruptions of a specific volcano? … you get the idea.

**Limit Experimentation**

Don’t over-use your validation set. If you try too many different techniques, and use a hold-out set to compare between them, be aware of the statistical power of the results you are getting, and be aware that the performance you are getting on this set is not a good estimator for out of sample performance.

**Do clean up your data**

With small data sets, noise and outliers are especially troublesome. Cleaning up your data could be crucial here to get sensible models. Alternatively you can restrict your modeling to techniques especially designed to be robust to outliers. (e.g.  [Quantile Regression](https://en.wikipedia.org/wiki/Quantile_regression))

**Do perform feature selection**

I am not a big fan of explicit feature selection. I typically go for regularization and model averaging (next two points) to avoid over-fitting. But if the data is truly limiting, sometimes explicit feature selection is essential. Wherever possible, use domain expertise to do feature selection or elimination, as brute force approaches (e.g. all subsets or greedy forward selection) are as likely to cause over-fitting as including all features.

**Do use Regularization**

Regularization is an almost-magical solution that constraints model fitting and reduces the effective degrees of freedom without reducing the actual number of parameters in the model.  **L1 regularization**  produces models with fewer non-zero parameters, effectively performing implicit feature selection, which could be desirable for explainability of performance in production, while  **L2 regularization**  produces models with more conservative (closer to zero) parameters and is effectively similar to having strong zero-centered priors for the parameters (in the Bayesian world). L2 is usually better for prediction accuracy than L1.

![](https://miro.medium.com/max/554/1*CwnSVcr9rZa3pllDrRP71Q.png)

**Do use Model Averaging**

Model averaging has similar effects to regularization is that it reduces variance and enhances generalization, but it is a generic technique that can be used with any type of models or even with heterogeneous sets of models. The downside here is that you end up with huge collections of models, which could be slow to evaluate or awkward to deploy to a production system. Two very reasonable forms of model averaging are Bagging and Bayesian model averaging.

![](https://miro.medium.com/max/630/1*LQYmYT1t4QqGGnho-zVe0g.png)
Each of the red curves is a model fitted on a few data points

![](https://miro.medium.com/max/630/1*-RadM0WAtEHd0HIAxQAawQ.png)
But averaging all these high variance models gets us a smooth output that is remarkably close to the original distribution [Pattern Recognition and Machine Learning](http://research.microsoft.com/en-us/um/people/cmbishop/prml/webfigs.htm)

**Try Bayesian Modeling and Model Averaging**

Again, not a favorite technique of mine, but Bayesian inference may be well suited for dealing with smaller data sets, especially if you can use domain expertise to construct sensible priors.

**Prefer Confidence Intervals to Point Estimates**

It is usually a good idea to get an estimate of confidence in your prediction in addition to producing the prediction itself. For regression analysis this usually takes the form of predicting a range of values that is calibrated to cover the true value 95% of the time or in the case of classification it could be just a matter of producing class probabilities. This becomes more crucial with small data sets as it becomes more likely that certain regions in your feature space are less represented than others. Model averaging as referred to in the previous two points allows us to do that pretty easily in a generic way for regression, classification and density estimation. It is also useful to do that when evaluating your models. Producing confidence intervals on the metrics you are using to compare model performance is likely to save you from jumping to many wrong conclusions.

![](https://miro.medium.com/max/630/1*WoZICSUtmuWhblYksKnoqg.png)
Parts of the feature space are likely to be less covered by your data and prediction confidence within these regions should reflect that

![](https://miro.medium.com/max/630/1*vBLM1uU-N8HTi2X0GURoVw.gif)

Bootstrapped performance charts from [ROCR](http://rocr.bioinf.mpi-sb.mpg.de/)

## Summary

This could be a somewhat long list of things to do or try, but they all revolve around three main themes:  constrained modeling, smoothing and quantification of uncertainty.

Most figures used in this post were taken from the book  [“Pattern Recognition and Machine Learning”](http://research.microsoft.com/en-us/um/people/cmbishop/prml/)  by  [Christopher Bishop](http://research.microsoft.com/en-us/um/people/cmbishop/index.htm).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTUxOTk5NTY4NF19
-->