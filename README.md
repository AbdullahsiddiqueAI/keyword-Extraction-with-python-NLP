

# Text Processing and Keyword Extraction README
# # Before Proceeding
Ensure you have the necessary libraries installed:

numpy for linear algebra
pandas for data processing
nltk for natural language processing
sklearn for machine learning models
# # Introduction
This project demonstrates the preprocessing of text data and extraction of keywords from a collection of research papers. The dataset used consists of the first 5000 records from a CSV file named papers.csv.

# # Dataset
The dataset contains research papers with the following columns:

title: Title of the paper
abstract: Abstract of the paper
paper_text: Full text of the paper
Data Preprocessing
Working with "paper_text"
The preprocessing steps applied to the paper_text include:

Lowercasing the text
Removing HTML tags
Removing special characters and digits
Tokenizing the text
Removing stopwords
Removing words with less than three letters
Lemmatizing the words
Steps to Preprocess Text
Lowercase: Convert all characters to lowercase.
Remove HTML tags: Use a regular expression to remove HTML tags.
Remove special characters and digits: Use a regular expression to retain only alphabetic characters.
Tokenize: Split the text into individual words.
Remove stopwords: Remove common stopwords from the text.
Remove short words: Discard words with less than three characters.
Lemmatize: Reduce words to their base form.
# Vectorization
CountVectorizer
The CountVectorizer is used to convert the text data into a matrix of token counts. Parameters used:

max_df=0.95: Ignore terms with a document frequency higher than 95%.
max_features=5000: Use the top 5000 most frequent words as features.
ngram_range=(1, 2): Extract unigrams and bigrams from the text data.
TF-IDF
TF-IDF (Term Frequency-Inverse Document Frequency) is used to weigh the importance of words. Important parameters:

smooth_idf=True: Add 1 to document frequencies to prevent zero divisions.
use_idf=True: Enable IDF to give higher weight to less frequent words.
Keyword Extraction
Explanation of Functions
sort_coo(coo_matrix)
Sorts the sparse COO (Coordinate List) matrix in descending order based on the TF-IDF values.

extract_topn_from_vector(feature_names, sorted_items, topn=10)
Extracts the top n items from a sorted list of index-value pairs and returns a dictionary of feature names and their corresponding scores.

Main Code Workflow
Fetching Feature Names: Retrieve feature names (vocabulary) from CountVectorizer.
Generating TF-IDF Vector: Create the TF-IDF vector for a given document.
Sorting TF-IDF Vectors: Sort the TF-IDF vectors by descending order of scores.
Extracting Top Keywords: Extract the top 10 keywords for a given document.
Printing Results: Print the title, abstract, and extracted keywords for a specified document.
Saving the Model
The trained CountVectorizer and TfidfTransformer models, along with the feature names, are saved using pickle for future use.

# Conclusion
This README provides an overview of text preprocessing, vectorization, and keyword extraction from research papers using pandas, nltk, and sklearn. The steps outlined ensure the effective transformation of text data into meaningful features for further analysis.