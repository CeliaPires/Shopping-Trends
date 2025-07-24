# **Shopping trends and customer behaviour analysis**
## *Celia Pires*


![Project image cover](images/dataset-cover.jpg)



## **Project introduction**


* This dataset provides a detailed snapshot of online shopping behaviour and consumer trends. It contains synthetic yet realistic customer profiles with various features such as age, gender, purchase categories, payment preferences and engagement with promotional offers. 

* The dataset can be found in Kaggle: [dataset](https://www.kaggle.com/datasets/sahilislam007/shopping-trends-and-customer-behaviour-dataset). 

* License: (CC0) Public domain


## Dataset content

* 3900 rows
* 18 columns
* File type: csv



| **Column** | **Description** |
| --------------------------- | --------------------------------------------- |
| **Unnamed column** | Indexed column |
| **Customer ID** | Unique identified for each customer |
| **Age** | Age of the customer |
| **Gender** | Gender of the customer (Male / Female/Other) |
| **Item purchased** | Name of the item bought |
| **Category** | Category of the item (e.g., Clothing, Footwear) |
| **Purchase amount (USD)** | Total amount spent in USD |
| **Location** | Location where the purchase occurred |
| **Color** | Preferred color of the item |
| **Season** | Season in which the purchase was made |
| **Review rating** | Customer review score (scale: 1.0 to 5.0) |
| **Subscription status** | Whether the customer is subscribed to a membership plan (Yes/No) |
| **Shipping type** | Chosen method of shipping (e.g., Express, Free Shipping, Next Day Air) |
| **Discount applied** | Whether a discount was used in the transaction (Yes/No) |
| **Promo code used** | Whether a promo code was applied (Yes/No) |
| **Previous purchases** | Number of past purchases made by the customer |
| **Payment method** | Payment method used (e.g., Credit Card, PayPal, Venmo, Cash) |
| **Frequency of purchases** | Stated frequency of shopping (e.g., Weekly, Monthly, Annually) |


## **Business requirements**

### **Business goals: promotion response**

* Which segments are more likely to respond to promotional events (i.e., use promo codes or discounts)?

* What customer attributes correlate with higher spending during promotions?


## **Promotional response hypotheses and how they will be validated**


| **Hypothesis** | **Test Type** | **Validation**
|-----------------------------------------------------|------------------------------------------------------|------------------------------------------------------|
| H1: **Younger customer groups** (e.g., Gen Z, Millennials) **use promo codes more often than older groups** | Chi-squared test | Promo code usage across age segments |
| H2: **Female customers are more likely to use discounts than male customers** | Chi-squared test | Gender vs discount usage |
| H3: **Customers who use discounts tend to spend more per purchase** | Independent two-sample t-test | Compare purchase amounts (discounted vs not) |
| H4: **Season affects promotion response** (e.g., more promo code use during Winter Sales) | Chi-squared test | Season vs promo code usage |

### **Rationale for test type used**

* The Chi-squared test is used to test associations between two categorical variables. 

* When comparing means (averages) of a numeric variable (purchase_amount_(usd)) between two independent groups (discount_applied = yes or no), the t-test is the statistically correct approach.


### **Summary outcome**


| **Hypothesis** | **What we tested** | **What we found** | **Conclusion** |
|-----------------------------------------------------|------------------------------------------------------|------------------------------------------------------|------------------------------------------------------|
| H1 | **Younger customer groups** (e.g., Gen Z, Millennials) **use promo codes more often than older groups** | Not statistically significant | Not supported  |
| H2 | **Female customers are more likely to use discounts than male customers** | Statistically significant | **Not supported** (pattern in dataset contradicts the hypothesis result) |
| H3 | **Customers who use discounts tend to spend more per purchase** | Not statistically significant | Not supported |
| H4 | **Season affects promotion response** (e.g., more promo code use during Winter Sales) | Not statistically significant | Not supported |


## **Project plan**

* During the ideation and organisation phase, I brainstormed a series of user stories with milestones and deadlines to ensure that the overall deadline for completion was met. I also agreed the data cleanse and transformation strategy.

* This is the high level plan I came-up with:

| **Milestone** | **Task** | **Deadline**
|-----------------------------------------------------|------------------------------------------------------|------------------------------------------------------|
| **Project set-up** | Select project idea | **18/07/25** |
| **Project set-up** | Create github repository | **18/07/25** |
| **Project set-up** | Kanban board set-up | **18/07/25** |
| **Project set-up** | VS Code project set-up | **18/07/25** |
| **ETL** | Data load/preparation | **21/07/25** |
| **Data analysis** | Hypothesis testing | **22/07/25** |
| **Data analysis** | Customer segmentation| **22/07/25** |
| **Data visualisation** | Generate insights | **23/07/25** |
| **Project closure** | Project documentation | **24/07/25** |


* The detail of the project Kanban board can be found here: [Kanban board](https://github.com/users/CeliaPires/projects/9/views/1?visibleFields=%5B%22Title%22%2C%22Assignees%22%2C%22Labels%22%2C%22Milestone%22%5D)


## **The rationale to map the business requirements to the data visualisations**

* The project's aim is to analyse online shopping behaviour using a range of customer attributes and purchase activities. The dataset included demographic details (age, gender), transaction characteristics (item, category, purchase amount, season) and behavioural indicators (discount and promo code usage, subscription status, review ratings and purchase frequency).

* The core business objective is to understand which customer segments are most responsive to discounts and promotions and whether these offers influence spending behaviour. To achieve this, several hypotheses were tested to uncover patterns in promo code and discount usage across different demographic and transactional variables.

* To support these goals, data visualisations were carefully chosen to help stakeholders interpret key findings.

* Although none of the hypotheses were statistically supported, the visualisations provided valuable context and helped visualise unexpected patterns such as gender-based discount trends that contradict common assumptions. These insights can inform future campaigns by encouraging the business to challenge biases and test promotional strategies more systematically.

* Ultimately, the visual approach ensured findings were accessible to non-technical stakeholders and aligned closely with the project's aim to deliver actionable insights into customer behaviour through data-driven storytelling.


## **Analysis techniques used**

* **Descriptive statistics** to summarise and explore general trends (eg, Mean purchase amount, frequency counts of promo usage, distribution of age and gender).

* **Data visualisation** to identify patterns and communicate insights visually (boxplots, stacked bar charts).

* **Hypothesis testing** to assess statistical significance of observed relationships (eg, Chi-Squared Test, t-Test).

* **Clustering** to group customers with similar behaviours (eg, K-Means Clustering, DBSCAN).

* **Data cleaning and preparation** to ensure data quality and integrity before analysis (eg, removing PII).

* **Feature engineering** to create new variables that add meaning or improve analysis (eg, "age group" from raw age).


## **Ethical considerations**

* Already covered in the miscellaneous section under points 6.2 and 6.1.


## **Dashboard Design**

* For data visualisation, chose to use Power BI (PBI). Due to limitations with the version of PBI being used, a link cannot be provided. However, a file is available in the **Dashboards** folder labelled **shopping_trends**.

![PBI desktop confirmation](images/pbi-desktop-confirmation.png)


In PBI, chose 4 visualisations that correlate to the business goals: increase sales through marketing campaigns.

Since hypothesis testing highlighted issues with the quality of the data, changed some of the parameters to produce the visualisations.

For all the visualisations, **changed the parameter for purchase_amount_(usd) from 'sum' to ''average'** to produce insightful insights.


![Visualisation summary](images/visualisation-summary.png)


**1. Stacked bar chart: average of purchase_amount_(usd) by location**

This first graph shows the average spend by location. By hoovering over the graph, you will be able to see the values individually. I was interested to see if there where areas were marketing campaigns had proven to be more impactful than others. As you can see, the average spend ranges from $59.42 in New Hampshire (lowest) to $67.60 in Alaska (highest), a difference of only $8.18 which is not significant considering how expensive marketing campaigns are. So here, I would say that the average spend is the same across all regions.


**2. Line and stacked column chart: average of purchase_amount (usd) by season**

Using the line and stacked column chart, I was interested to see if marketing campaigns had had any significant impact on average spend by season (I purposely changed the variable from promo_code_used from hypothesis testing to average_spend_usd). Once again the results show that there are no differences across seasons. It ranges from $58.41 in the summer (lowest) to $61.66 in the fall (highest), a marginal difference of $3.25. As an example, when we know that Black Friday is a big event in the US and companies tend to slash their prices to increase revenue, I was surprised to see no difference across seasons. There are only 3 case scenarios here: either the company did not run any promotional events, or they did run and there was no ROI or the dataset is incorrect. Before jumping to any conclusions, had this been in a real working environment, I would have checked the accuracy of the data first before jumping to any conclusions.

**3. Donut chart: average of purchase_amount (usd) by age group**

The donut chart shows average spend by age group (changed the variable from promo_code_used from hypothesis testing to average_spend_usd). Again, you can see in the graph that there are no differences across customer segments and average spend which is unusual.

**4. Clustered bar chart: average of purchase_amount (usd) by gender**

The clustered bar chart shows average spend by gender. For this one, I chose to change the variable from discount_applied from hypothesis testing to average_spend_usd. Again, there is no difference in average spend across genders (average spend is roughly $60). I had always heard females to be higher spenders compared to males. Again, I would challenge the accuracy of the data when you also take into account the method of payment. If you hoover over the graph, you will see a tooltip I created and added to the graph that shows the method of payment by count of transactions. Again, I see some inconsistencies here. For females, the 3 main methods of payment are: credit card, paypal and cash. For males, cash, debit card and paypal. In Kaggle, the summary of the dataset mentions "**online** shopping behaviour". When shopping online, I struggle to understand how a customer can make payments using cash or even "bank transfer". This additional finding highlights once again that the data might not be correct. 

**5. Text filter based on location**

This last visualisation provides a quick way to view data by filtering on the location. If I type in "Utah" as an example and press "enter" all the graphs automatically update to only show data related to that location. 


![Filter by location](images/filter-by-location.png)


## **Unfixed Bugs**

Fortunately, there are no unfixed bugs to report on. This time round, I adopted a different strategy that incorporated lessons learnt from solo and group hackathons along with planning ahead for the capstone. My knowledge and understanding of the process has greatly improved which is rewarding to see. This time round I felt more in control. My checklist definitely helped and also reaching out to my fellow students as and when I was not sure of something was really reassuring. At the start of the project when I was trying to clone my repo in VS Code, I got confused with some of the steps. I reached-out to Natalie Waugh who very kindly provided guidance on what I needed to do. Same thing with Power BI where I felt that my knowledge was not where it needed to be. I reached-out to a couple of people in my cohort who were able to recommend YouTube content to address some of my gaps. Finally, during the capstone when I add to complete clustering for my dataset, reached-out to Spencer to validate my understanding and the interpretation of the results. In the process, realised how important the data cleanse/tranformation step is, more specifically when it comes to data re-engineering. I have definitely learned from it and will be more vigilent as and when I perform a similar type of work in the future.


## **Development roadmap**

Completing the Hackathons and the Capstone project has been a big learning curve for me. As I progressed through the bootcamp, I overcame the imposter syndrome and with it my knowledge and understanding of the process. That being said, there are 2 areas where I plan to develop further. The first one being Power BI. Although I am able to perform basic/simple visualisations, I feel there is more to learn and I have already identified a couple of videos on YouTube to help me with this. The second area is around consolidating my knowledge and understanding of machine learning. For this, I plan to revisit the content in the LMS and practice with datasets from Kaggle so that I can test various techniques and learn what works and what does not work.


## **Miscellaneous**

Pass criteria requirement **9.2 (Explain how data analytics and AI can address specific challenges or opportunities).**

Data Analytics & AI can help identify opportunities for business growth by uncovering patterns in the data, predicting outcomes to enable data-driven decisions. For example, in my dataset, data analytics uncovered an issue with the quality of the data. Had this happened in a real working environment, it would have triggered an investigation to either assess if the quality of the data is the issue or if past marketing campaigns have not produced the desired ROI. With a good, quality dataset with strong insights, AI models can help tailor marketing campaigns to drive operational efficiency and support strategic goals. 


Pass criteria requirement **8.3 (Explore relevant applications of data analytics in the chosen data domain, indicating a breadth of understanding and curiosity).**

In the context of retail/e-commerce, data analytics can play a pivotal role in uncovering insights to facilitate the decision-making process. Using my dataset as an example, had the data been accurate, by analysing transactional data, demographic patterns and engagement metrics companies can quickly identify high-value customer segments and forecast purchasing trends. Techniques such as clustering enables businesses to personalise promotions, optimise inventory and enhance the overall shopping experience. Data analytics not only helps solve real world problems it also helps uncover opportunities for growth through targetted marketing campaigns and ovrall operational efficiency.


Pass criteria requirement **8.1 (Articulate complex data insights to technical and non-technical audiences).**

Since my dataset was very straight forward, I kept the messaging purposely simple to tailor different audiences. For example for the hypotheses, I included technical and non technical content to aid with the understanding of the findings. I purposely included a table at the start of the hypotheses that provides the null and alternative hypothesis in plain emglish. I also inluded a section at the start explaining the key statistical terms. In the readme, provided a summary, again, very simple summarising the findings. From personal experience senior management does not like too much detail in presentations. The detail is best shared during project meetings as and when questions arise. In PBI, carried on with the theme by using simple graphs that are commonly used and kept the narrative jargon free to convey my findings. 


Pass criteria requirement **7.2 (Select research methodologies applicable to the project goals).**

For this project, I used an observational research methodology since the goal of the project was to identify high profile customer segments to drive sales through targetted marketing campaigns. During data analysis, I anonymised transaction records by removing the customer ID information. When it came to analyse the data, combined descriptive statistics to explore general trends (eg, mean spend per customer to understand average shopping behaviour, number of customers using promo codes to assess promotional response, box plots of spending by gender and age group to compare patterns across segments), clustering techniques to segment customers based on behaviour and hypothesis testing to uncover relationships between variables. These methodologies were specifically selected to support the project’s goal of understanding customer behaviour and identifying actionable insights to inform targeted marketing campaigns. 


Pass criteria requirement **6.2 (Discuss the legal and social implications of the data handling and findings).**

**6.1 (Examine ethical issues, data privacy, and governance in the project’s methodology).**

To comply with data privacy regulations such as the General Data Protection Regulation (GDPR), all personally identifiable information (PII) was removed from the dataset (eg, 'customer_id' column). This was key to protect individuals' privacy. The final dataset used for analysis was fully anonymised. 

From a legal perspective, GDPR emphasises transparency, data minimisation and purpose limitation. This means using only the data that is strictly necessary for the intended business purpose. In a real working environment, I would seek to obtain explicit user consent for the purpose of delivering my project. 

From a social perspective, I took into consideration ethical considerations by minimising biases in the analysis and jumping to conclusions too quickly, stereotyping genders behaviour in the process. Hence, why I made the point multiple times of going back to the data source to re-check the accuracy of the data before finalising my findings. It is important that when faced with poor quality data we document our analysis and we go back to the drawing ball (eg, request a new or corrected dataset) to ensure that we strip as much as possible biases in the data to minimise the risk of basing decisions that could contribute to discriminatory practices (eg, only offering promo codes to a specific gender).


Furthermore, I also considered key ethical issues around data privacy, bias and fairness. The dataset clearly had data quality issues which I thourougly reviewed and documented during exploratory phase to avoid skewed interpretations. The goal of the analysis was to understand customer behaviour in order to better tailor marketing campaigns/promotional events rather than targeting customers unfairly. I was very cautious on how I documented my findings. I followed strict governance practices such as highlighting data quality issues and mainly maintaining the integrity of the dataset (no data/columns were amended) to support responsible use of data.


Pass criteria requirement **4.2 (Apply generative AI solutions in storytelling with data.)**

I used AI throughout the project to generate ideas on how best to approach certain deliverables. The main area was around customer segmentation. Since this was all new to me, as I previously explained, I used chatgpt for guidance on how best to approach this. The codes/the visuals were all generated using AI Python code. I also used chatgpt to interpret the results and visualise the data (plot charts). My commentary is a combination of chatgpt's input and my own reflections. I also used chatgpt to draft the hypothesis and the business requirements/goals. 


Pass criteria requirement **3.2 (Evaluate the problem-solving approach and solutions proposed.)**

In addition to the very detailed problem-solving approach I took and thoughrouly documented in my 2 jupyter notebooks, the last issue that came to light today as I was closing down my activities is around user stories. For some strange reason, I was not able to edit the content of the user story to make amendements. Used the comments section instead to document what I wanted to write before closing the user story. I will need to investigate this later to understand what happened here.


## **Main Data Analysis Libraries**

* Pandas & Numpy to convert csv file into a DataFrame to facilitate the data cleansing/transformation process. 

* Scipy for statistical analysis and hypothesis testing.

* Matplotlib, seaborn & plotly for visualisation of the hypotheses.

* Sklearn for customer segmentation.


## **Credits**

**ULTIMATE Power BI tutorial beginner to pro course (2024)**: [pbi tutorial](https://www.youtube.com/watch?v=Dk25lwdTKow&t=10371s).
This YouTube tutorial helped me grasp the basics of PBI to complete the capstone project.


### **Content**

**Code Institute LMS programme** [LMS](https://learn.codeinstitute.net/ci_program/daai_9).
I used the LMS throughout the project to access Python code and overall learning content.


### **Media**

* The image used for the project introduction was taken from Kaggle [Project image intro](https://www.kaggle.com/datasets/sahilislam007/shopping-trends-and-customer-behaviour-dataset).


## **Acknowledgements**

**Jane Weightman** for sharing the breakfix for the Plotly issue.

**Natalie Waugh** for her support and guidance throughout the project.

**Emma Lamont** for her patience and support throughout the course and during the capstone project.

**Vasi Barriball** for deputising for Emma and helping me with my queries/issues with the sharing of the PBI desktop dashboard.











