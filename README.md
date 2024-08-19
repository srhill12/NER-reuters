# Named Entity Recognition and Analysis on Reuters Corpus

This project focuses on performing Named Entity Recognition (NER) and analyzing entities in the Reuters corpus using Natural Language Processing (NLP) tools. The goal is to extract, count, and analyze geopolitical entities (GPE) and organizations (ORG) mentioned in Reuters news articles, specifically those related to the "coffee" category.

## Project Overview

### Objectives

1. **Data Collection**:
   - Retrieve articles from the Reuters corpus related to the "coffee" category.
   - Preprocess the text data for entity recognition.

2. **Named Entity Recognition (NER)**:
   - Use spaCy's NER capabilities to identify and extract geopolitical entities (GPE) and organizations (ORG) from the articles.

3. **Entity Analysis**:
   - Count the frequency of each entity and identify the most common entities across the corpus.
   - Create visualizations to understand the distribution and prominence of these entities.

## Data Sources

- **Reuters Corpus**: The project utilizes the Reuters corpus from the NLTK library, specifically focusing on articles categorized under "coffee."

## Key Steps and Functions

### 1. Data Retrieval and Preprocessing

- **Load Reuters Corpus**: Articles from the Reuters corpus categorized under "coffee" are retrieved and stored for analysis.

- **Example Article**:
  ```python
  COLOMBIA COFFEE REGISTRATIONS REMAIN OPEN
  Colombia's coffee export registrations remain open and there are no plans to close them since a new
  marketing policy means an unlimited amount can be registered, Gilberto Arango, president of the private exporters'
  association said.
  ```

### 2. Named Entity Recognition (NER)

- **Using spaCy for NER**:
  - The spaCy library is used to analyze the text and identify entities such as persons, organizations, and geopolitical entities.
  - The entities are extracted using spaCy’s `doc.ents` and categorized by their labels (e.g., GPE for geopolitical entities, ORG for organizations).

- **Example NER Output**:
  ```python
  ['Patrick Mahomes ---> PERSON',
   'the Kansas City Chiefs ---> ORG',
   'the American Conference ---> ORG',
   'one ---> CARDINAL',
   'two ---> CARDINAL',
   'the National Football League ---> ORG']
  ```

### 3. Entity Extraction and Analysis

- **Extracting Entities**:
  - Entities are extracted from the text, specifically focusing on geopolitical (GPE) and organizational (ORG) entities.
  - Entities are cleaned by converting to lowercase and removing any newline characters.

- **Counting Entity Frequencies**:
  - The frequency of each entity is calculated using Python’s `Counter` from the collections module.
  - The most common entities across all "coffee" articles are identified.

- **Example Frequent Entities**:
  ```python
  [('brazil', 172),
   ('ico', 125),
   ('u.s.', 84),
   ('colombia', 81),
   ('london', 59)]
  ```

### 4. DataFrame Creation and Visualization

- **Creating a DataFrame**:
  - A DataFrame is created to store each entity and its frequency of occurrence.
  - The DataFrame is sorted to display the most common entities first.

- **Sample DataFrame Output**:
  ```python
  entity      frequency
  0   brazil          172
  1   ico             125
  2   u.s.            84
  3   colombia        81
  4   london          59
  ```

## Results

### Most Common Entities in "Coffee" Articles

- **Top Entities**: The most frequently mentioned entities in Reuters coffee-related articles are:
  - Brazil
  - ICO (International Coffee Organization)
  - U.S.
  - Colombia
  - London

- **Insights**:
  - Brazil is the most frequently mentioned geopolitical entity, reflecting its prominent role in global coffee production.
  - The ICO, as an organization, is heavily referenced in discussions about coffee trade and regulation.

### DataFrame Analysis

- The DataFrame provides a detailed view of how often each entity is mentioned, offering insights into the focus areas of coffee-related news in the Reuters corpus.

## Conclusion

This project demonstrates how NLP techniques, particularly NER, can be applied to extract and analyze entities from a large corpus of text. The analysis provides valuable insights into the entities most frequently associated with coffee-related news, highlighting key players in the global coffee industry.

## Requirements

- Python 3.x
- SpaCy
- NLTK
- Pandas

## Installation

To install the required libraries, use the following pip commands:

```bash
pip install spacy nltk pandas
python -m spacy download en_core_web_sm
```

## How to Run

1. Ensure all required libraries are installed.
2. Download the Reuters corpus using `nltk.download("reuters")`.
3. Load the small English language model for spaCy using `python -m spacy download en_core_web_sm`.
4. Run the script to perform NER and analyze entities in the Reuters coffee-related articles.

The analysis will output the most common entities and provide a DataFrame summarizing their frequencies across the corpus.
