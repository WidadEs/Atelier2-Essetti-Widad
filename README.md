# Atelier2-Essetti-Widad
## Part 1:Rule Based NLP and Regex
#### The provided code snippet demonstrates a simple text processing and parsing task to generate a bill from a user-provided text containing item descriptions, quantities, and prices. Here are some key points regarding the code's functionality and evaluation:
   ### 1-Text Cleaning Function (clean_text):
#### The clean_text function effectively removes stop words and extra whitespaces from the input text using regular expressions (re module).
#### Stop words are predefined and include common words like "I," "for," "and," etc., which are typically irrelevant for bill generation.
   ### 2-Bill Generation Function (generate_bill):
#### The generate_bill function parses the cleaned text to extract item names, quantities, and prices using regex patterns.
#### It converts quantity words (e.g., "one," "two," etc.) to numeric values and calculates total prices for each item based on quantity and unit price.
#### The generated bill table includes columns for "Product," "Quantity," "Unit Price," and "Total Price," providing a structured representation of the items and their costs.
   ### 3-Evaluation:
#### Regex Patterns: The regex patterns used for matching quantities, prices, and item names are effective for basic scenarios. However, they may need refinement for handling more complex cases (e.g., different price formats, multi-word item names).
#### Data Parsing: The code successfully extracts relevant information from the input text, demonstrating its ability to process structured data within unstructured text.
#### Numeric Conversion: The conversion of quantity words to numeric values and the calculation of total prices appear to work correctly, ensuring accurate billing information.
#### Output Format: The generated bill table format is clear and concise, presenting the necessary details in a tabular format suitable for billing purposes
  ### 4-Overall Impression:
#### The code provides a solid foundation for text-based bill generation, showcasing effective use of regex patterns and text processing techniques. It can be further enhanced by refining regex patterns to handle a wider range of input variations and by adding error handling for cases where data extraction may fail. Overall, it's a functional and practical solution for basic bill generation tasks from textual descriptions.

## Part 2: word Embedding 
### Applying one hot encoding, bag of words, TF-IDF technics on the Data vectors collected during the lab 1.
#### La partie du code que j'ai fournie se concentre sur l'utilisation de différentes techniques de vectorisation de texte sur des données extraites d'une base de données MongoDB.
  ### 1-One Hot Encoding (CountVectorizer(binary=True))
#### Le codage one-hot est une technique de représentation de texte qui transforme chaque mot en un vecteur binaire où chaque élément correspond à la présence ou à l'absence du mot dans le document.
#### La paramètre binary=True signifie que chaque mot sera représenté par un 0 ou un 1, indiquant s'il est présent ou non dans le document.
  ### 2-Bag of Words (CountVectorizer()) 
#### Le modèle sac de mots (BoW) est une méthode qui représente chaque document par un vecteur où chaque élément représente le nombre d'occurrences d'un mot dans ce document.
#### Le CountVectorizer sans paramètres supplémentaires par défaut produit une représentation BoW.
  ### 3-TF-IDF (TfidfVectorizer()) 
#### TF-IDF est une technique qui évalue l'importance d'un mot dans un document par rapport à une collection de documents.
#### Le TfidfVectorizer calcule les scores TF-IDF pour chaque mot dans les données textuelles.
### Applying one Word2Vec Approach (Skip Gram, CBOW) on the same DataSet.
  ### 1-Tokenisation des données
#### Les données sont déjà divisées en mots/tokenisées (tokenized_data).
  ### 2-Création des modèles Word2Vec 
#### Deux modèles Word2Vec sont créés : Skip Gram et CBOW.
#### Ces modèles apprennent à représenter les mots dans des vecteurs de 100 dimensions en analysant le contexte des mots dans les données tokenisées.
#### Le modèle Skip Gram se concentre sur la prédiction des mots environnants, tandis que CBOW prédit un mot à partir de son contexte.
  ### 3-Accès aux vecteurs de mots
#### Les vecteurs de mots sont obtenus à partir des modèles entraînés (skipgram_model.wv et cbow_model.wv).
#### L'exemple montre comment obtenir le vecteur du mot 'زلزال' (séisme) dans chaque modèle.

#### En résumé, cette partie illustre comment créer des modèles Word2Vec avec Gensim, les entraîner sur des données tokenisées et accéder aux vecteurs de mots résultants, qui peuvent être utilisés pour diverses tâches de traitement du langage naturel, comme la similarité des mots ou la classification basée sur les embeddings de mots.

### Applying Glove and FastText approaches on the same DataSet
#### En résumé, cette partie utilise FastText pour créer des embeddings de mots basés sur des données tokenisées. Il crée deux modèles avec des stratégies d'entraînement différentes (Skip Gram et CBOW) et permet d'accéder aux vecteurs de mots pour des mots spécifiques dans chaque modèle. FastText est particulièrement utile pour la gestion des mots hors vocabulaire et la capture des relations sémantiques même pour les mots rares ou les fautes de frappe grâce à son traitement des sous-mots.

### Ploting all the encoded / vectorized vectors by using Tsne Algorithm, evaluate those approaches and give a general conclusion.
  ### 1-Code Explanation:
#### The code defines a function plot_vectors_3d that takes vectors and a model name as input, performs t-SNE dimensionality reduction to 3D, and plots the vectors in a 3D scatter plot.
#### It then calls this function to plot the vectors of the one hot encoded, bag of words, and TF-IDF matrices in 3D space.
  ### 2-General Conclusion:
#### The conclusion states that word embedding techniques like Word2Vec, GloVe, and FastText capture semantic relationships between words, making them suitable for natural language processing (NLP) tasks where understanding word meanings and context is important.
#### TF-IDF is highlighted as useful for representing the importance of words in a document, which is valuable for tasks like document classification or keyword extraction.
#### Bag of Words and one hot encoding are mentioned as simpler techniques that do not consider word order but can still be effective in certain contexts where the focus is more on word presence rather than meaning or context.

#### Overall, the code provides a visual comparison of different vectorization techniques and offers a concise conclusion about their strengths and use cases in NLP tasks.
