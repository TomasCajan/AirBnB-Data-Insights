# AirBnB-Data-Insights

#### Welcome to the Undacity Data Scientist Nanodegree capstone project 1 - a data science blogpost.<br>
This excercise is meant to practice making data driven decisions.<br>
The dataset we're about to analyze is available at    https://www.kaggle.com/datasets/airbnb/boston/data <br>
Since this dataset was used quite many times, a creative approach was selected to find some non-trivial questions about this dataset and answer them using data. <br>

-------------

**Scenario :** <br>
Meet Alex, a young Data Scientist, living in Boston, in the Roxbury neighbourhood. Alex is a happy owner of a nice apartment.<br>
Alex is currently planning his vacation. He would like to travel arround the world for full 2 months.<br>
That is quite expensive fun however, even for Alex, so he is trying to figure out, how to reduce the costs of his vacation. He does not really care when he goes for the vacation, for as long as it lasts 2 months.<br>
Alex gets an idea - how about he rents his apartment while he is away, using the AirBnB. The rent could pay good portion of his travel expenses.<br>

You can read about his adventures with AirBnB below.

![Project Diagram](images/DalleAlex.png)

You already heard that Alex would like to rent his apartment using AirBnB.<br>
However Alex knows nothing about AirBnB and renting at all.<br>
Good thing he's a Data Scientist! He can make the data talk and help him. Alex has 3 questions about the rent that make him curious the most.<br>
Answering them should help in decision making about how and when to rent.
With the Kaggle Boston AirBnB dataset in his hands, Alex is ready to crack the mystery of a successful renting with AirBnB.<br>

#### 3 main questions Alex has before he is ready to rent his apartment :<br>

**Question 1** : When is the optimal time to rent his apartment, for him to make the most money from the rent?

**Question 2** : How are his chances to rent his apartment for full two months compared to apartments in other city neighbourhoods?

**Question 3** : What are the main factors influencing customers, who would rent such apartment? What can he do to improve his chances to attract people or earn more from rent?

-------------

**Question 1** : When is the optimal time to rent his apartment, for him to make the most money from the rent?<br>

To answer this question, Alex has to use his coding and statistics skills to filter data specificaly according to his needs.

- He has two dataframes, one containing rent prices and the other rent time periods, he needs to join them together first.
- The only time data he has available are timestamps of rents, therefore he has to divide his data into months.
- He has to filter the dataframe by location, to include only his neighborhood - Roxbury.
- And finaly he has to visualize the pair of months, where the expected rent price is the highest.

![Project Diagram](images/Q1.png)
- And there's the answer! It looks like Alex can make the most money from rent in period June-July.

-------------

**Question 2** : How are his chances to rent his apartment for full two months compared to apartments in other city neighbourhoods?

To answer this, Alex has to use his filtering and visualization skills again, this time in a different setting.

- He performs the steps he did to answer the previous question
- Then additionaly he has to filter the data only for those rent records, that lasted at least 60 days to be relevant.
- And also limit the filtering only for those staring in June, because that is when we wants to start the rent.
- Finaly he has to compare the ammount of rent listings for all neighborhoods with the filtered dataset and visualize the result.

![Project Diagram](images/Q2.png)

And there is the answer Alex is looking for  - we can observe that the ammounts of rents per neighbourhood are roughly separated into 3 categories - high, medium and low.<br>
Alex ranked in the medium category - not bad, not great.<br>
Alex definintely has good chances to rent his apartment, however he should use all the advantages he could get to satisfy his customers needs to attract them.<br>
His next question will help him with that!<br>

-------------

**Question 3** : What are the main factors influencing customers, who would rent such apartment? What can he do to improve his chances to attract people or earn more from rent?

It's finaly time for Alex to showcase his machine learning skills, because to answer this question, he will need a trained machine learning model.
Machine learning model can show its feature importances, in other words identify categories it considers important when predicting.
This can lead Alex to points, that can help him understand the customers behaviour and preferences.

Alex is a fan of XGBoost machine learning model, so he utilizes it to train it on his data and assess its feature importances.

![Project Diagram](images/Q3_1.png)

There are many categories the model is trained on. While the model considers them important, by far not all of them will be relevant to Alex.<br>
Because it is his first rent listing, all the reviews based categories won't help him anyhow.<br>
The categories that describe type of the house and location are also not very helpful, since Alex isn't going to move just because renting his apartment better.<br>
But still, he can find some hints about what to work on.<br>

SHAP values are a great tool for understanding how the model decides. In this case, how to understand how value of categories manipulates the price.
Alex can use it to learn: <br>

- How can allowing guests into the rented apartment influence the price people are willing to pay for the rent.
  
![Project Diagram](images/Q3_2.png)

The figure shows that allowing at least 3 guests into the apartment can increase the price people are willing to pay for the rent. Simple thing to do.

- How does bed count in the apartment matter?

![Project Diagram](images/Q3_3.png)

Having only one bed, which is Alex's case, is not a desired option for many. Good thing there's a furniture store in the next street, so Alex can buy a new one.

- What kinds of verifications do people appreciate the most?
  There are several ways he can use, like Facebook, LinkedIn, Jumio, or kba.

![Project Diagram](images/Q3_4.png)

  


