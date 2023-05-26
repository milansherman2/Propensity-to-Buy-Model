# Propensity-to-Buy-Model
<h2>Binary Classification</h2>
<p><b>Note</b>: this was a collaborative project with one other person in the class.  We both generated and reviewed models and code, discussed results, and crafted and presented results.</p>

<p>
  <b>Problem</b>: 
  The problem that we were trying to solve is predicting whether a user approved for a life insurance policy with Sherman’s company
  would purchase a policy.  Given that only 30-40% of users who apply for a policy are approved, this is an important group of
  potential customers for the company to focus on as they’ve already cleared an important barrier to becoming a customer by getting
  approved.

  </p>
  
<b>Implications</b>: 
1.	Being able to predict who will purchase a policy can help to allocate resources in terms of following up with users who are approved but have not bound, i.e., purchased, a policy.  Currently the marketing action that the company is taking with these customers is to have an agent contact the user via phone to follow up and answer questions.  
2.	Knowing the characteristics of users who are likely to bind can guide future marketing and product development.  
I was especially interested in understanding the importance of a particular feature to the model in this project related to how the software generates insurance premium quotes.  I did an analysis that found that more than half of users are shown a higher premium after they are approved than they saw when they generated an instant quote at the start of the process.  By including the difference between these two premiums as a feature in the model and understanding its importance to the accuracy of the model, the company can begin to quantify how this feature is impacting the business and take appropriate action.

<b>Solution</b>: 
One advantage of working with a partner was that we were able to explore more models than if we'd been working individually.  In particular, this was my first experience implementing and tuning TabNet, CatBoost, and ensemble models.  The best model varied depending the metric we used, with the following results:
- Best Accuracy (86.4%): CatBoost
- Best Recall (83%): TabNet Classifier
- Best Precision (86%): Random Forest
- Best F1 (83%): CatBoost and Ensemble model

Ultimately, we decided that F1 was the best metric for our problem, as we wanted to control for both false positives and false negatives, and the target was imbalanced (about one-third of approved users purchase a policy).  Given the simnplicity the CatBoost model vs. the Ensembe model, we decided that the CatBoost model was probably the best option to develop further.

Another question that was posed in this project was the importance of the feature that measured the difference in premiums that users saw between their quoted price and the price for the product that they were approved for. Using both the raw difference in premiums as well as the difference as a percent of the quoted premium, we investigated the importance of these features using several methods:
<ul>
  <li>Feature importance in various models</li>
    <ul>
      <li>Recursive feature extraction</li>
    </ul>
  </li>
  <li>Examining purchase rate across premiums, i.e., do users tend to purchase at a higher rate when they don’t see a higher premium after being approved regardless of the magnitude of the premium?  This allowed to separate the issue of the size of the premium difference vs. size of the premium in understanding what influences users' decision to purchase.</li> 
</ul>

We found that this feature was consistently one of the Top 10 features in terms of feature importance in these models. <br>
<b>Note</b>: another project in this portfolio, <i>Multiclass Classifification: Predicting Approved Risk Class</i>, demonstrates how I solved the problem of users seeing a higher price after being approved.


<h2>Languages Used</h2>

- <b>SQL</b> 
- <b>Python</b>

<h2>Models Used </h2>

- <b>K Nearest Neighbors (KNN)</b>
- <b>Logistic Regression</b>
- <b>Decision Tree</b>
- <b>Random Forest Classifier</b>
- <b>TabNet (Neural Network for tabular data)</b>
- <b>Catboost</b>
- <b>Ensembe Model (KNN, Logistic Regerssion, Decision Tree, and Random Forest)</b>

<h2><a href="https://github.com/milansherman-usa/Multiclass-Classification-Model/blob/main/Approved%20Risk%20Class.pdf" target="_blank">Jupyter Notebook (pdf)<a/></h2>
