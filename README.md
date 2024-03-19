# Data/ML Engineer Assignment: Vector Database API for PDF Documents
**Implement text extraction to convert the PDF documents into text data**
To implement text extraction and convert PDF documents into text data, I would use the Python along with the PyPDF2 library. PyPDF2 is a widely-used library that allows us to extract text from PDF documents.

**1.Installation:** Install the PyPDF2 library:
```python
pip install PyPDF2
```
**2.Importing libraries:** Import the necessary libraries:
```python
import PyPDF2
```
**3.Load the PDF document:** Assuming have a PDF document named "sample.pdf" in the same directory as the script, open and load the document using the PyPDF2 library:
```python
pdf_file = open('sample.pdf', 'rb')
pdf_reader = PyPDF2.PdfFileReader(pdf_file)
```
