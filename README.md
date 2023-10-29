# Project Name: Document Similarity Model for Mining Reports
A tremendous volume of data is generated every day, these data are stored in varying formats. In our project, the documents (WAMEX PDF file) from the Department of mining, WA, which stores information about the Nickle mines in the Kambalda region serve as input.
Our aim was to generate a model, that could predict documents similar to the inputted documents, based on the similarity of the content within the document. 


## Project Tasks Performed:
### Task 1: Annotation

The initial step of the project involved manually annotating 40 documents. Here's how we accomplished it:

1. We converted the PDF documents into images using online PDF converters.
2. These image files, which represented pages from the PDFs, were then imported into Data Torch, a powerful platform designed for manual annotation.
3. In Data Torch, we manually annotated each document by drawing bounding boxes around content areas and assigning appropriate labels to these boxes.
4. The annotated images were then converted into JSON files within Data Torch, resulting in 40 annotated JSON files.

### Task 2: TF-IDF Score Calculation

To measure the content similarity between the annotated documents, we calculated TF-IDF (Term Frequency-Inverse Document Frequency) scores for tokens extracted from the "Table of Contents" section of each document. The process was as follows:

1. We used PDFminer to extract the text from the "Table of Contents" section of each document.
2. TF-IDF scores were computed for each token. TF-IDF assigns more weight to words that are frequent within a PDF but rare across all documents.
3. These TF-IDF scores were utilized to create a cosine similarity matrix between all the documents. This matrix helps identify the top N similar reports when given a target WAMEX PDF file name.

### Task 3: Webpage Development

We designed a user-friendly webpage using the Python library "Gradio" to output the names and short descriptions of sections abstracts for reports similar to the input WAMEX PDF file. The webpage includes three input fields:

1. File name: The name of the WAMEX PDF file you want to find similar reports for.
2. File path: The path to the directory containing the WAMEX PDF files.
3. Number of similar documents: The desired number of similar reports to generate.

## Files in the Repository

  - TF_IDF_Metadata_v2.ipynb: Finial code which contains the backend integrated with 
Ui
  - UI.ipynb: Jupyter Notebook contains the code for developing the user interface (UI)
  - annotated_file-20231029T075214Z-001.zip: The zip file contains JSON files resulting from the annotation process. These JSON files represent the annotated data for a set of documents.
  -  tfidf.ipynb: This Jupyter Notebook which contains code to calculate TF-IDF.





