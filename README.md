# Data/ML Engineer Assignment: Vector Database API for PDF Documents
**Implement text extraction to convert the PDF documents into text data**
To implement text extraction and convert PDF documents into text data, I would use the Python along with the PyPDF2 library. PyPDF2 is a widely-used library that allows us to extract text from PDF documents.

**1. Installation:** Install the PyPDF2 library:
```python
pip install PyPDF2
```
**2. Importing libraries:** Import the necessary libraries:
```python
import PyPDF2
```
**3. Load the PDF document:** Assuming have a PDF document named "sample.pdf" in the same directory as the script, open and load the document using the PyPDF2 library:
```python
pdf_file = open('sample.pdf', 'rb')
pdf_reader = PyPDF2.PdfFileReader(pdf_file)
```
**4. Extract text from the PDF:** Iterate through each page of the PDF document and extract the text content using the extractText() method:
```python
text_content = ''
for page_num in range(pdf_reader.numPages):
    page = pdf_reader.getPage(page_num)
    text_content += page.extractText()
```
**5. Clean the extracted text:** Depending on the specific requirements, I can apply text preprocessing techniques such as tokenization, stop word removal, stemming, or lemmatization to further clean the extracted text data. For example, to remove line breaks and unnecessary whitespaces, I use the following code:
```python
text_content = text_content.replace('\n', ' ').replace('\r', ' ').strip()
```
**6. Save the extracted text:** Save the extracted and cleaned text data to a file or use it for further processing as needed:
```python
with open('extracted_text.txt', 'w') as file:
    file.write(text_content)
```
**Reasoning behind the approach:** *I chose to use the PyPDF2 library because it is widely used, easy to install, and provides a simple API for extracting text from PDF documents.

I decided to load the PDF document using the PdfFileReader class of the PyPDF2 library, which allows us to access individual pages and extract content.
To extract text, I used the extractText() method provided by the getPage() function of the PyPDF2 library.*

**Apply text preprocessing techniques such as tokenization, stop word removal, stemming, and lemmatization to clean the extracted text data.**

To apply text preprocessing techniques such as tokenization, stop word removal, stemming, and lemmatization to clean the extracted text data, I will follow the following steps:


**1. Tokenization:**
Tokenization is the process of breaking a text into individual words or tokens. I'll use the NLTK (Natural Language Toolkit) library in Python to perform tokenization.

**Reasoning:** *NLTK is a widely used library for natural language processing tasks and provides efficient tokenization methods.*


**2. Stop Word Removal:**
Stop words are commonly used words that do not carry much meaning and can be safely removed from the text. I'll utilize NLTK's stop words corpus to remove these words from the tokenized text.

**Reasoning:** *Stop word removal helps in reducing noise and unnecessary information, allowing the focus to be on important words.*


**3. Stemming or Lemmatization:**
- Stemming and lemmatization are techniques used to reduce words to their base or root form. I will use the NLTK library to perform stemming or lemmatization based on the requirements.

**Reasoning:** *Stemming and lemmatization help in standardizing words and reducing the vocabulary size, improving the efficiency of further processing and analysis.*


**4. Cleaning and Transformation:**
- After performing the above preprocessing techniques, I'll clean the text data by removing any special characters, numbers, or punctuation marks that may still be present.

**Reasoning:** *Cleaning the text data ensures that only relevant and meaningful words are retained, eliminating any noise that may interfere with further processing.
By applying these text preprocessing techniques, we can obtain clean and transformed text data that is ready for vector representation and further analysis.*


