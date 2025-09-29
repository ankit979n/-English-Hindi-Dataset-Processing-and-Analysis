**Assignment 1 – Dataset Processing and Analysis**
Objective: Process a parallel English–Hindi dataset, filter sentences based on word count rules, and prepare a cleaned dataset.


Steps
Load Dataset: 
    Read eng.txt and hin.txt files.
    Store sentences into a DataFrame with two columns: English, Hindi.

Preprocessing: 
    Strip extra whitespace.
    Limit to 10,000 rows.

Tokenization & Word Counts
    Define a tokenize() function to split sentences into words.
    Count words in each English and Hindi sentence.

Filtering Rules

    Keep only sentences where word counts are between 5 and 50 in both languages.
    Calculate difference in word counts between English and Hindi.
    Keep only pairs where the difference lies between -10 and +10.

Save Output
    Export the final cleaned dataset to cleaned_dataset.xlsx.


Summarizing the logic or main idea:
In Assignment 1, the task begins with two raw text files: eng.txt containing English sentences and hin.txt containing their Hindi counterparts. 
These files are read and combined into a single dataset using Python and Pandas. We then preprocess the dataset by trimming whitespace and restricting it to 10,000 rows. 
Each sentence is tokenized using a custom tokenize() function to split text into words while removing punctuation. For every English and Hindi sentence, word counts are calculated. 
To maintain consistency and remove extreme cases, only those sentence pairs are retained where both English and Hindi word counts lie between 5 and 50. 
Additionally, the difference in word counts between the two languages is computed, and only those pairs with a difference between -10 and +10 are kept. 
The final cleaned dataset is saved into an Excel file named cleaned_dataset.xlsx, which contains the English sentence, Hindi sentence, word count for each, and the difference. 
This ensures that the dataset is balanced, filtered, and ready for further translation tasks.
     ***Total sentences I got after cleaning: 8210***


**Assignment 2 – Translation with LLM**
Objective: Translate 100 English sentences into Hindi using a Large Language Model and evaluate translation quality.

Steps:
Select Sentences
    Load cleaned_dataset.xlsx from Assignment 1.
    Randomly select 100 English sentences.

Translate with LLM
    Use Hugging Face model: Helsinki-NLP/opus-mt-en-hi.
    Input English → Output Hindi translation.

Evaluate Translations
    Compare model-generated Hindi with reference Hindi from dataset.
    Compute scores using sacrebleu:
      BLEU Score
      CHRF Score
      TER Score
    Save scores in translation_scores.txt.

Save Output
    Export results to translation_output.xlsx with:
    Column A → English sentence
    Column B → Model-generated Hindi translation

Summarizing the logic or main idea:
In Assignment 2, the cleaned dataset from Assignment 1 serves as the input. From this dataset, 100 English sentences are randomly selected for translation. 
To perform translation, we use a Large Language Model (LLM) provided by Hugging Face (Helsinki-NLP/opus-mt-en-hi), which is specifically trained for English-to-Hindi machine translation. 
Each English sentence is passed through the model, and the generated Hindi translation is recorded. The quality of these translations is then evaluated against the reference Hindi sentences 
from the dataset using the sacrebleu library, which calculates standard machine translation evaluation metrics: BLEU, CHRF, and TER scores. These scores are written into a text file called translation_scores.txt 
to document the overall translation performance. Finally, the English sentences and their model-generated Hindi translations are saved into an Excel file named translation_output.xlsx for easy 
viewing and verification.





***BLEU Score: 11.465496299543915,   
CHRF Score: 32.17189095938202,   
TER Score: 85.99242833964304***


