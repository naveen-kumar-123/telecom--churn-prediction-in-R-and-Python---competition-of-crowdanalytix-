# Telecom Churn Analysis and Prediction in R
<b>link to the data</b> - https://www.crowdanalytix.com/contests/why-customer-churn/
----------------

<b>Description:</b>  
Churn (loss of customers to competition) is a problem for telecom companies because it is more expensive to acquire a new customer than to keep your existing one from leaving. This contest is about enabling churn reduction using analytics.

 

<b>The Business Plan:</b>  
Most telecom companies suffer from voluntary churn. Churn rate has strong impact on the life time value of the customer because it affects the length of service and the future revenue of the company. For example if a company has 25% churn rate then the average customer lifetime is 4 years; similarly a company with a churn rate of 50%, has an average customer lifetime of 2 years. It is estimated that 75 percent of the 17 to 20 million subscribers signing up with a new wireless carrier every year are coming from another wireless provider, which means they are churners. Telecom companies spend hundreds of dollars to acquire a new customer and when that customer leaves, the company not only loses the future revenue from that customer but also the resources spend to acquire that customer. Churn erodes profitability.

 

<b>Steps that have been adopted by telecom companies so far:</b>  
Telecom companies have used two approaches to address churn - (a) Untargeted approach and (b) Targeted approach. The untargeted approach relies on superior product and mass advertising to increase brand loyalty and thus retain customers. The targeted approach relies on identifying customers who are likely to churn, and  provide suitable intervention to encourage them to stay.

 

<b>Role of predictive modelinng:</b>  
In the targeted approach the company tries to identify in advance customers who are likely to churn. The company then targets those customers with special programs or incentives. This approach can bring in huge loss for a company, if churn predictions are inaccurate, because then firms are wasting incentive money on customers who would have stayed anyway. There are numerous predictive modeling techniques for predicting customer churn. These vary in terms of statistical technique (e.g., neural nets versus logistic regression versus survival analysis), and variable selection method (e.g., theory versus stepwise selection).

 

<b>Objective of this Contest:</b>  
The objective of this contest is to predict customer churn. We are providing you a public dataset that has customer usage pattern and if the customer has churned or not. We expect you to develop an algorithm to predict the churn score based on usage pattern. The predictors provided are as follows:

<ol>
	<li>account length in days</li>
	<li>had international plan or not</li>
	<li>had voice mail plan or not</li>
	<li>number of voice mail messages a person made</li>
	<li>total day minutes used</li>
	<li>day calls made</li>
	<li>total day charge</li>
	<li>total evening minutes</li>
	<li>total evening calls</li>
	<li>total evening charge</li>
	<li>total night minutes</li>
	<li>total night calls</li>
	<li>total night charge</li>
	<li>total international minutes used</li>
	<li>total international calls made</li>
	<li>total international charge</li>
	<li>number of customer service calls made</li>
</ol>
 

<b>Target Variable:</b>  
Churn: if the customer has churned (1=yes; 0 = no)
----------------

<b>Analysis Results:</b> 
Some of the observations that I had made during EDA and things customers had done before having churned are:
<ul>
	<li>Customers that churned the most are the ones that called customer service more.</li>
	<li>Most customers that had been charged more had called customer service more.</li>
	<li>Old customers didn't churn as much as the new ones did.</li>
	<li>Charge for used minutes wasn't directly proportional to number of minutes used sometimes, which can't happen in real world. (<i>data and the description didn't have much information on how this data was collectd. so, couldn't figure out what actually might have caused this.</i>)</li>
</ul>

----------------

<b>Prediction Results:</b>  
For my analysis, recall was the target metric, (measure the proportion of all correctly predicted customers that churned)
We care the most about capturing as many true positives (people who are likely to churn) with our model, and we’re less concerned that we may sweep in some false negatives (people who did not churn) along with them.  
Logistic Regression and Random Forest Classification has been used for prediction.
The Recall, Precision , F1 Score and Accuracy reports are
<table style="width:100%">
  <tr>
	  <th>algorithm</th>
	  <th>Recall</th>
	  <th>Precision</th>
	  <th>F1 Score</th>
	  <th>Accuracy</th>
  </tr>
  <tr>
	  <th>Logistic Regression</th>
	  <td>97%</td>
	  <td>87%</td>
	  <td>91.73%</td>
    	  <td>86.55%</td>
  </tr>
  <tr>
    	  <th>Random Forest Classification</th>
	  <td>94%</td>
	  <td>99%</td>
	  <td>96.43%</td>
	  <td>94.48%</td>
	  
  </tr>
</table>
  
So, from the above results, it's obvious that,  
<ol>
	<li>Logistic Regression' was relatively able to better capture/predict the customers that are likely to churn(recall) compared to Random Forest. But, not the ones that were not likely to churn and overall customers as well.</li>
	<li>Random Forest's model could capture/predict a healthy mix of both, as given by F1 Score.</li>
</ol>
