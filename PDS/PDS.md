
![[Pasted image 20251020114240.png]]


![[Pasted image 20251020115159.png]]


## . **What is an n-gram?**

An **n-gram** is a sequence of ‘n’ items (usually words) from a given text or speech.

- **Unigram:** 1 word at a time.  
    Example: "Data Science" → ["Data", "Science"]
    
- **Bigram:** 2 words at a time.  
    Example: "Data Science is fun" → ["Data Science", "Science is", "is fun"]
    
- **Trigram:** 3 words at a time.  
    Example: "Python for Data Science" → ["Python for Data", "for Data Science"]
    

**Use:**  
N-grams help analyze text for patterns (like frequent phrases, predicting next word, sentiment analysis).

---

## 2. **Explain the TF-IDF Technique**

## **TF-IDF** stands for **Term Frequency - Inverse Document Frequency**

It is a statistical measure used to evaluate how important a word is to a document in a collection (corpus).

## **Steps:**

**A. Term Frequency (TF):**

- Measures how often a term appears in a document.
    
- Formula:  
    TF=Number of times term appears in document
	Total terms in documentTF=Total terms in document
	Number of times term appears in document
    

**B. Inverse Document Frequency (IDF):**

- Measures how important a term is across the entire corpus.
    
- Formula:  
    IDF=log⁡e(Total number of documentsNumber of documents with term)IDF=loge(Number of documents with termTotal number of documents)
    

**C. TF-IDF Calculation:**

- Multiply TF and IDF for each word.
    
- Words common to many documents (like "the", "and") get lower scores, while unique or rare words get higher scores.
    

## **Example:**

Suppose we have 3 documents:

- doc1: "Python for data science"
    
- doc2: "Data science uses python"
    
- doc3: "Python is popular"
    

Calculate TF-IDF for the term "python":

- TF for "python" in doc1 = 1/4 (since 4 words)
    
- IDF = log(3/3) = 0 (since "python" appears in all docs)
    
- TF-IDF for "python" = (1/4) * 0 = 0 (not unique across docs)
    

But, if a word appears only in one document, its TF-IDF score will be higher!

**TF-IDF is heavily used in text mining, search engines, and natural language processing to find keywords and represent documents numerically for analysis**



# Groupby function in [python]

![[Pasted image 20251021200009.png]]




# bag of words
The Bag of Words (BoW) model is a fundamental and simple technique in Natural Language Processing (NLP) used to convert text into numerical form for machine learning tasks such as text classification, sentiment analysis, and document clustering. It represents a text document as an unordered collection ("bag") of words, focusing only on the frequency of each word’s occurrence while ignoring grammar, word order, and syntax.[](https://www.geeksforgeeks.org/nlp/bag-of-words-bow-model-in-nlp/)​

## How Bag of Words Works

1. **Vocabulary Building:** The process begins by creating a vocabulary of all unique words from the entire dataset (all documents in the corpus). Each unique word corresponds to a feature in the model.[](https://www.engati.com/glossary/bag-of-words)​
    
2. **Vector Representation:** Each document is then represented as a vector with the length equal to the size of the vocabulary. Each dimension or element of this vector corresponds to a specific word from the vocabulary, and its value is the count (frequency) of that word in the document.[](https://builtin.com/machine-learning/bag-of-words)​
    
3. **Ignoring Word Order:** The model does not record the order of words or grammatical information; it only captures how many times each word appears in a document. This makes the method simple and computationally efficient but limits its ability to capture context or semantics.[](https://en.wikipedia.org/wiki/Bag-of-words_model)​
    

## Example

Given two documents:

- Document 1: "John likes to watch movies. Mary likes movies too."
    
- Document 2: "Mary also likes to watch football games."
    

The vocabulary might be: 

["John", "likes", "to", "watch", "movies", "Mary", "too", "also", "football", "games"]

Document 1 vector:

- {"John":1, "likes":2, "to":1, "watch":1, "movies":2, "Mary":1, "too":1, "also":0, "football":0, "games":0}
    

Document 2 vector:

- {"John":0, "likes":1, "to":1, "watch":1, "movies":0, "Mary":1, "too":0, "also":1, "football":1, "games":1}[](https://en.wikipedia.org/wiki/Bag-of-words_model)

![[Pasted image 20251021201657.png]]



## What is Z-score Standardization?

- **Z-score standardization** (also called standard score or normalization) is a technique to scale numeric features by removing the mean and scaling to unit variance.
- the means the mean will be 0 and standard deviation will be 1 
    
- Formula:
    
    z=(x−μ)/σ 

    - x: original value
        
    - μ: mean of the feature
        
    - σ: standard deviation of the feature
        

---

## Why Do We Need Z-score Standardization in EDA?

- **Removes Bias from Scale:** Features with different units or scales can bias the analysis and learning algorithms.
    
- **Makes Features Comparable:** Standardization allows fair comparison and combination of features.
    
- **Required by Algorithms:** Many ML algorithms (like KNN, SVM, Logistic Regression) assume that all features are centered around zero and have the same variance.
    
- **Better Visualization:** Standardized data helps in better visualization and outlier detection.
    

---

## Example

Suppose we have a small dataset of student heights (in cm):

| Student | Height (cm) |
| ------- | ----------- |
| Arun    | 170         |
| Priya   | 160         |
| Ravi    | 180         |

- **Mean (μ)(μ)**: (170+160+180)/3=170(170+160+180)/3=170
    
- **Standard Deviation (σ)(σ)**: ≈8.16
    

Now, Z-scores:

- Arun: (170−170)/8.16=0(170−170)/8.16=0
    
- Priya: (160−170)/8.16≈−1.22(160−170)/8.16≈−1.22
    
- Ravi: (180−170)/8.16≈1.22(180−170)/8.16≈1.22
    

So, after standardization:

| Student | Z-score |
| ------- | ------- |
| Arun    | 0       |
| Priya   | -1.22   |
| Ravi    | 1.22    |

---

**Summary:**

- **Z-score standardization** re-scales all features to have mean 0 and standard deviation 1, making them comparable and suitable for many statistical and ML tasks.



## **What is Data Wrangling?**

**Data wrangling** (also called data munging) is the process of cleaning, transforming, and organizing raw data into a structured, usable format for analysis or modeling.

- The aim is to turn messy, incomplete, or unstructured data into a dataset ready for analysis.
    
- It’s a crucial early step in any data science or machine learning workflow.

![[Pasted image 20251022194623.png]]




## **Covariance**

- **Covariance** measures how two variables change together.
    
- If both variables increase together, covariance is positive. If one increases and the other decreases, it is negative.
    

**Formula:**

![[Pasted image 20251115183708.png]]

- XiXi, YiYi: individual values
    
- XˉXˉ, YˉYˉ: means of XX and YY
    
- nn: number of observations
    

**Interpretation:**

- Positive covariance: variables tend to move together.
    
- Negative covariance: variables move in opposite directions.
    
- Value depends on the scale of data.
    

---

## **Correlation**

- **Correlation** measures the strength and direction of a linear relationship between two variables.
    
- Unlike covariance, correlation is scale-independent (always between -1 and 1).
    

**Formula (Pearson correlation):**

![[Pasted image 20251115183847.png]]

- σXσX, σYσY: standard deviations of XX and YY
    

**Interpretation:**

- r=+1r=+1: perfect positive correlation
    
- r=−1r=−1: perfect negative correlation
    
- r=0r=0: no linear relationship




## **Stemming: Definition**

- **Stemming** is a text preprocessing technique used in Natural Language Processing (NLP) to reduce words to their base or root form.
    
- The root (stem) may not always be a valid word, but it enables the grouping of related words for analysis.
    

---

## **Concept Explanation**

Stemming strips suffixes or prefixes from words, converting them to a standard base form.  
For example:

- "playing", "played", "plays" → "play"
    

This reduces the vocabulary size and helps algorithms treat variations of the same word as one.

Example: 

from nltk.stem import PorterStemmer
stemmer = PorterStemmer()
words = ["playing", "played", "plays", "player"]
stemmed_words = [stemmer.stem(word) for word in words]
print(stemmed_words)



## Skewness and Kurtosis: Concepts

- **Skewness** measures the asymmetry of a data distribution.
    
    - Positive skew: longer tail on right.
        
    - Negative skew: longer tail on left.
        
    - Zero skew: symmetric distribution.
	        
- **Kurtosis** measures the "tailedness" or how peaked/flat the distribution is compared to a normal distribution.


# EDA
![[Pasted image 20251101161730.png]]
![[Pasted image 20251101161741.png]]
![[Pasted image 20251101161753.png]]


# Numpy VS Panadas

| Aspect            | NumPy                                             | Pandas                                        |
| ----------------- | ------------------------------------------------- | --------------------------------------------- |
| Primary Data Type | Multi-dimensional homogeneous arrays              | Series and DataFrames with heterogeneous data |
| Purpose           | Numerical computations and scientific computing   | Data manipulation and analysis                |
| Performance       | Faster for numerical operations, memory efficient | Slightly slower; optimized for large datasets |
| Data Handling     | Numerical data                                    | Tabular, labeled, and structured data         |
| Features          | Mathematical, linear algebra functions            | Data cleaning, grouping, reshaping, file I/O  |
| Use Cases         | Math-intensive tasks, machine learning backend    | Data analysis, exploratory data work          |


# Slicing and Dicing 

**Slicing** means selecting a range or subset from the DataFrame based on position or labels. For example, using `.loc[]` or `.iloc[]`, you can slice rows or columns by label or integer position:

- `.loc[start_label:end_label]` slices rows (inclusive of endpoints) based on index labels.
    
- `.iloc[start_pos:end_pos]` slices rows based on integer position (start inclusive, end exclusive).  
    Example: `df.loc[1:3]` selects rows with index labels 1 to 3, and `df.iloc[:, 0:2]` slices the first two columns.
    

**Dicing** is a more general term that refers to filtering or selecting subsets based on multiple criteria — such as picking multiple columns and rows simultaneously or based on conditions. It can involve complex filtering with boolean indexing and label-based indexing to "cut" the data into smaller, focused pieces.


# Magic Functions or Dunder methods
special type of functions that are used to perform custom tasks 
they are defined with  "_ _funName_ _" double underscore at start and end 

we can use them to define custom behaviours of some builtin functions like 
operators , len, call etc


# Magic functions in jupyter notebook

%matplotlib inline
%timeit
%pwd


# Three levels of flat file dataset

![[Pasted image 20251102110327.png]]


# Linestyles in plot

![[Pasted image 20251102110745.png]]

![[Pasted image 20251102110713.png]]

# Hashing Trick

- The **hashing trick** is a method for efficiently converting text data (such as words or n-grams) into a fixed-length vector representation, without needing to create a dictionary or explicit mapping of each token to an integer index.
    
- It uses a **hash function** to map each unique word or feature to a column in the resulting feature vector.
    
- This is especially useful for handling very large vocabularies (such as in natural language processing), since you don’t have to store or look up the entire list of all tokens.

## **Why Use the Hashing Trick in Scikit-learn?**

- **Memory Efficiency:** No need to save full vocabulary; just store vector length and rely on hash function.
    
- **Speed:** Faster to compute and less overhead in preprocessing.
    
- **Streaming:** Works well for very large datasets or data streams, where new tokens might continuously arrive

![[Pasted image 20251102121410.png]]


# NetworkX 

**NetworkX** is a popular Python library used for the **creation, manipulation, and study of complex networks and graphs**.

## Key Features:

- **Graph Types:** Supports undirected, directed, and multigraphs (graphs with multiple edges between nodes).
    
- **Easy Graph Operations:** You can add, remove, and query nodes and edges easily.
    
- **Graph Algorithms:** Includes many built-in algorithms for _shortest path_, _clustering_, _connectivity_, _centrality_, and more.
    
- **Visualization:** Basic graph visualization capabilities (for more advanced, you can use with matplotlib).
    
- **Data Import/Export:** Graphs can be read from and written to different formats (like adjacency lists, edge lists, GraphML, etc.).
    
- **Analysis:** Widely used for network analysis in fields like social network analysis, biology, computer science, transportation, etc.



# Regression

**Regression** is a statistical and machine learning technique used to model and analyze the relationship between a dependent (target) variable and one or more independent (predictor) variables. The most common type is **linear regression**.

---

## Key Points:

- **Goal:** Predict a continuous value (like price, temperature, marks, etc.).
    
- **Types:**
    
    - **Simple Linear Regression:** One predictor.
    - **Multiple Linear Regression:** More than one predictor
    - Polynomial Linear Regression

Linear Rgeression finds the line y = mx+b such that it is closest to all the data points 


# Feature Engineering

	Feature engineering is the process of turning raw data into useful features that improve the performance of machine learning models. It involves selecting, creating, transforming, and adjusting data attributes to make the predictions more accurate and the models more efficient.

# Feature Scaling

	Feature scaling is a process of bringing all the feature or columns in a sames scale. like cgpa and salary, both are on different scale , so for better performance and accuracy we bring them on a same scale generally , 0 to 1 or -1 to 1
	we dont need to do scaling all the time , some algorithms work good even without scaled data but some require data to be on the same scale.


# Normalization and Standardization

both are feature scaling techniques . 

standardization also called  z score standardization and also called mean centering 
in standardization we bring the data at the center or origin of the graph , where mean becomes zero and standard deviation becomes 1 for all the values. 

and all the values comes in the range of  -1 to 1
formula is , Xi - mean/ standard deviation 
	z=(x−μ)/σ 

![[Pasted image 20251104162649.png]]

## Normalization has different techniques , like
		-Min max scaling
	     -robus scaling
	     -max absolute scaling
	 mostly used is min max scaling 
	 where all the values comes in the range of 0 to 1
	formula is  Xi = (Xi-minval)/(maxval-minval)

![[Pasted image 20251104163021.png]]

# Feature encoding

feature encoding is a process of converting all the data into numbers because models or computer only understands numbers they dont understand strings or words 

we have different types of data 
		Categorical data
				-Nominal data
				 - Ordinal data
nominal data does not have any order all the values are same 
ordinal data have different order , wehre one is smaller or greater than other value

We use 
		Nominal data -> one hot encoding 
		 Ordinal data -> ordinal encoding

and for output column or target feature we specifically use 
			-> Label encoding
we cant use label encoding for input columns 


## Ordinal encoding 
in ordinal encoding  we simply assign the values based on the order of data 
like we have poor, avg ,good, best  so -> 0,1,2,3


## One hot encoding
In one hot encoding we create different columns for each data or feature 

for example we have one columns representing color 
color = yellow blue green yelllow green green blue blue ...
so we will create 3 columns                           yellow green blue 
if there is a yellow color then vector will be     1         0        0



# Column Transformer

to jab ham simple encoding lagate hain , aur hamare data ,me sari columns ek hi traha ki nahi hoti like ek ordinal hai ek nominal hai ek simple numerical hai to har column me alag alag encoding lagani padti hai jo ki kaafi hectic and complex kaam hai.

Isi problem se bachne ke liye hai COLUMN TRANSFOMER jo ki sare data me ek hi baar me ek sath alag alag encoding apply kar deta hai 


# Machine learning Pipeline

to shuru se last tak ML me bahut sare steps hote hain , data cleaning preprocessing scaling feature encoding etc to ye sab karna padta hai shuru me fir jab model ban jata hai to usko server pe dalte hain to aane wale input data pe bhi ye sab karna padta hia jo ki kaafi hectic task hota hai
aur ek galti aur sab khatam , isliye ye sab na ho isliye ham use karte hain 
ML pipeline
ML pipeline aisa process hai jisme multiple steps ko jod diya jata hai kuchh is tarike se ki ek step ka output agle step ka input ban jata hiai , aur ye piepline same process ko training and testing data me apply karne ko easy bana deta hai 


# Reading data from database


from sqlalchemy import create_engine
import pandas as pd
engine = create_engine("sqlite:///my_database.db")
df = pd.read_sql_table("employees", engine)
df_query = pd.read_sql("SELECT name, salary FROM employees WHERE salary > 50000", engine)
print(df_query)



![[Pasted image 20251115181234.png]]

1. df_no_duplicates = df.drop_duplicates(keep="last")



