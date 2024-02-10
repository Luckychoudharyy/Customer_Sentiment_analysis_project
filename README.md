# Customer_Sentiment_analysis_project

## Project Overview 
The British Airways Customer Reviews Analysis project aimed to assess customer sentiment across various aspects of the airline's service. Utilizing data sourced from the open internet, we compiled and structured it within Excel for analysis. Parameters such as food quality, entertainment options, and cabin staff services were examined to derive average ratings. These findings were then visualized using Tableau, providing a clear and concise overview of customer perceptions to inform strategic decision-making within the airline.

---

# `Ask`

#### Business Problem Statement
British Airways strives to maintain its position as a leader by prioritizing customer satisfaction. However, amidst the deluge of online feedback, extracting actionable insights has become a daunting task. To address this challenge, we propose the British Airways Customer Reviews Analysis project. Leveraging data from diverse online sources, we'll meticulously scrutinize customer sentiment regarding food quality, entertainment, and cabin staff services. Through advanced data analysis in Excel and visualization in Tableau, we aim to distill valuable insights. These insights will not only pinpoint areas of excellence and improvement but also fuel strategic decision-making to elevate the overall customer experience.

#### KPIs Required
We need to analyze key indicators for our customer review data to gain insights. Specifically, we want to calculate the following Average metrics:
1. Overall Ratings
2. Cbain Staff Services
3. Entertainment
4. Food and Bevrages
5. The Ground Service
6. Seat comfort
7. Value for money

#### Guiding Questions 
- Stakeholders anticipate answers to various critical questions through this analysis, including:

1. What are the key drivers of customer satisfaction and dissatisfaction?
2. How does customer sentiment vary across different aspects of service, such as food quality, entertainment, and cabin staff interactions?
3. Are there specific trends or patterns in customer feedback that indicate areas for improvement or opportunities for innovation?
4. How do customer sentiments differ across different demographic groups or customer segments?

---

# `Prepare`

The Primary dataset used for this analysis is the [ba_reviews](https://1drv.ms/x/s!AjKhR_ndv-LThnATL7s8TrpYVN5B?e=vtQymG) and [Countries](https://1drv.ms/x/s!AjKhR_ndv-LThnLk6qQY57KHOF7W?e=LeQhO3) Excel workbooks.
The Data was downloaded from Github and orignally sourced from someother open sourse websside. The Data has low credibility but the resulting analysis when validated with the internet resourses regarding the available Client information, Data seemed to agree with it. The data was raw and extremely dirty and needed cleaning and extraction. It was **cleaned** in **Excel** and was converted into individual CSV files for our comfort and ofcourse hands-on-practice with Data, then imported in **Tableau** and used **Joins** technique to retrieve appropriate information.

---

# `Process`

### Tools Used

- **Tableau** :- Joins, Dynamic complex Filtering, Advanced Custom metrics & parameter builds, Dynamic Visualisations
- **Microsoft Excel** :- Data cleaning and Initial Data Processing using VBA techniques

#### **Cleaning Process:**
   - Maintained a detailed data cleaning log in Excel
   - Resized, removed blanks, combined from two different datasets using **VBA** techniques.
     
#### **Data Integrity Assurance:**
   - cross-referenced the dataset with other sources and conducted spot checks to ensure accuracy and completeness, detecting any outliers or discrepancies.
   - Before downloading, reviewed the structure and format of the dataset to ensure it aligned with expectations, looking for inconsistencies or irregularities that might indicate potential data integrity issues.
  
## Excel VBA code used to combine datasets

```VBA

Sub GetSheets()
'Update ExcelJunction.com
Path = "C:\Users\lucky\OneDrive\Desktop\Datasets\"
Filename = Dir(Path & "*.xls")
Do While Filename <> ""
Workbooks.Open Filename:=Path & Filename, ReadOnly:=True
For Each Sheet In ActiveWorkbook.Sheets
Sheet.Copy After:=ThisWorkbook.Sheets(1)
Next Sheet
Workbooks(Filename).Close
Filename = Dir()
Loop
End Sub

```
### Result :

![Screenshot 2024-02-10 233138](https://github.com/Luckychoudharyy/Customer_Sentiment_analysis_project/assets/157785333/94caf06a-75ba-4ee0-ade6-a407b1a7db79)

#### After combining the two datasets, regorous cleaning and Data Manipulation was done and the data was then converted into CSV files to feed it to Tableau.

---

# `Analyse`

### Data Join in Tableau

![Screenshot 2024-02-10 234229](https://github.com/Luckychoudharyy/Customer_Sentiment_analysis_project/assets/157785333/3b857e0f-ac4a-4e0e-8f3f-36165c03fc01)

#### And

![Screenshot 2024-02-10 234248](https://github.com/Luckychoudharyy/Customer_Sentiment_analysis_project/assets/157785333/7c17a9a5-5eee-4651-8fdf-39880d6a5bfb)

#### Dataset result example after Join

![Screenshot 2024-02-10 234317](https://github.com/Luckychoudharyy/Customer_Sentiment_analysis_project/assets/157785333/72922f96-e159-4e3f-a14e-53b3b573b30c)

and this list goes long and long...

### Creating Advanced Parameters In Tableau

Advanced Parameters according to the KPIs defined above

![Screenshot 2024-02-11 000324](https://github.com/Luckychoudharyy/Customer_Sentiment_analysis_project/assets/157785333/2b926bd8-57dd-495e-99b3-265ddaed95d0)

#### Defined a calculated field to further process

``` 
CASE [Pick a Metric]
WHEN 'Overall Rating' THEN [Rating]
WHEN 'Cabin Staff Service' THEN [Cabin Staff Service]
WHEN 'Entertainment' THEN [Entertainment]
WHEN 'Food' THEN [Food Beverages]
WHEN 'Seat Comfort' THEN [Seat Comfort]
WHEN 'Ground Service' THEN [Ground Service]
WHEN 'Value' THEN [Value For Money]
END
```
with the use of CASE function fields were defined.

### Filters were defined to get the specific information

![Screenshot 2024-02-11 001116](https://github.com/Luckychoudharyy/Customer_Sentiment_analysis_project/assets/157785333/f659fd59-6871-4318-be8b-fd869427a089)

## Charts Prepared

1. Map

![Screenshot 2024-02-11 001654](https://github.com/Luckychoudharyy/Customer_Sentiment_analysis_project/assets/157785333/8db171f3-276e-4828-ba8b-da16476e1a6a)

2. KPI summary

![Screenshot 2024-02-11 001849](https://github.com/Luckychoudharyy/Customer_Sentiment_analysis_project/assets/157785333/d1d62345-c944-4311-8e33-0878b6c809b2)

3. Months Chart

![Screenshot 2024-02-11 002035](https://github.com/Luckychoudharyy/Customer_Sentiment_analysis_project/assets/157785333/774cad06-53e5-4f4f-aba0-639875553fe0)

4. Airplanes

![Screenshot 2024-02-11 002252](https://github.com/Luckychoudharyy/Customer_Sentiment_analysis_project/assets/157785333/6c037c37-7882-4de2-b037-aa15c0b98fe7)


### From this analysis we got to know a lot of information that the Data kept hidden.

# `Share`

Introduction:

As we transition into the sharing phase of our analysis for the British Airways Customer Reviews project, it's imperative to reflect on the journey thus far. We've diligently collected and analyzed customer feedback from various online platforms, scrutinizing every aspect of their experiences with British Airways. Now, armed with insightful findings and actionable insights, we stand poised to disseminate our discoveries and collaborate with stakeholders to drive strategic decision-making and enhance the airline's overall customer experience.

## The Dynamic Visualisation

![Screenshot 2024-02-11 002926](https://github.com/Luckychoudharyy/Customer_Sentiment_analysis_project/assets/157785333/33e66ae1-d4d3-4c87-acf0-a48210222895)





