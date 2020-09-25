# <div align="center">Predicting Passenger Survival</div>

## <div align="center">Project Overview</div>
Skills Demonstrated: *random forest, exploratory data analysis, feature engineering, text analysis*<br/>
Libraries and Programs: *Python, Jupyter Notebook, pandas, pivot_table, numpy, regex, seaborn*<br/>

Using the Titanic competition dataset available on Kaggle<sup>1</sup>, I created a model to predict which passengers would survive the 1912 sinking of the Titanic. The dataset included passenger attributes such as Name, Age, Sex, and Economic Class, as well as information about their trip, such as their Cabin, Embarkment Location, and Ticket Price.<br>

## <div align="center">Exploratory Data Analysis</div>
### 1. Know Your Data
I like to begin an analysis by learning some basics about the dataset (Figure 1). I want to know its shape (.shape), its column names (.columns), and its contents (.sample(), .describe(), .info(), .value_counts()).<br> 

**Figure 1.** Ten sample rows from the 'train' dataset.<br>

![alt_text](https://github.com/nphorsley59/Predicting_Passenger_Survival/blob/master/Figures/train_sample.png "'train' sample")<br>

Once I have a good understanding of the dataset, I start to visualize some of the distributions and explore relationships I think might be informative (Figure 2, 3). I use Seaborn (such as .distplot(), .barplot(), .boxplot(), and .scatterplot()) for straight-forward visualizations and Matplotlib.pyplot for visualizations that require more flexibility. When I need to group data by several features, I use pivot tables (.pivot_table()).<br>

**Figure 2.** A passenger's probability of surviving the wreck was non-random. It appears to be dependent on attributes such as age, sex, and economic class.<br>

![alt_text](https://github.com/nphorsley59/Predicting_Passenger_Survival/blob/master/Figures/agesexclass_survivalrate.png "Attributes Predicting Survival")<br>

**Figure 3.** Survival also varied by embarkment location, even when controlling for economic class. Why would this be?<br>

![alt_text](https://github.com/nphorsley59/Predicting_Passenger_Survival/blob/master/Figures/embarkment_ptable.png "Did Embarkment Location Matter?")<br>

### 2. Streamline Your Data
Next, I like to clean and organize my dataset so it is easy to work with. This includes tasks like dealing with NULL values, checking for errors, transforming skewed features, renaming unintuitive columns or values, removing outliers, and engineering new features.<br>

For this dataset, I listed out six tasks:
- Address Nulls
- Split 'Cabin' into deck and room number
- Split 'Name' into title and last name
- Use 'Ticket', 'ParCh', and 'SibSp' to determine if passengers were alone or in a party
- Rename, drop, and re-order columns
- Convert ordered factor columns to numeric<br>

**Figure 4.** I used the string matching libarary, re, to separate deck and room number in 'Cabin'.<br>

![alt_text]("Splitting 'Cabin' into 'Deck' and 'Rm_Num'")<br>

**Figure 5.** 'Title' was easy to pull from 'Name' but included a lot of low frequency results ("Col", "Jonkheer", "Rev"). I reduced 'Title' to values that occurred more than 10 times and changed all outliers to "Other".<br>

![alt_text]("Splitting 'Name' into 'Title' and 'Last'")<br>

### 3. Strategize for Modeling

I conclude Exploratory Data Analysis by bringing everything I've learned about the dataset together to prepare for modeling. I like to identify important features in the dataset, drop any data that won't benefit the model, and brainstorm a few promising modeling approaches.

## <div align="center">Modeling</div>

## <div align="center">Resources</div>
<sup>1</sup> https://www.kaggle.com/c/titanic <br/>
<sup>2</sup> https://www.encyclopedia-titanica.org/cabins.html <br/>
