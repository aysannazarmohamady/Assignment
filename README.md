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
