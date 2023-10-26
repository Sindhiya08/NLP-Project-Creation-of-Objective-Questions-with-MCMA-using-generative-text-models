# NLP-Project-Creation-of-Objective-Questions-with-MCMA-using-generative-text-models

_Cloning the repo to access the pdf from the Dataset folder_

_Importing the necessary libraries - Transformers, Pypdf_

*PDF Extraction*

Extracting the content of the PDF files to text using pypdf library

PYPDF

>It is one of the built-in python library to work with PDF files such as Extracting text, Merging, Editing etc...

>Version: 3.16.4

>Only extracting the Text hence importing PDFReader. File handling method is used to open the pdf, rb- as the file have images etc.

len()- To check the total num of pages 

For loop is used to read the content of all the pages in the pdf

Steps in Generating Q&A

1. Analyzing the content
2. Identifying Keywords
3. Transformers
4. Q&A generation

T5 model- Text To Text Transfer Transformer
 *t5-small model is used*

- Setting up the input string with placeholders(here we are using 4 placeholders- Question,Answer,Options,Content)

- Content -> the extracted text will be passed in to this as a passage to generate Question,Answer & Options

- Tokenize and encode the input text, Encoded input will be stored in input_ids

- Have set the maximum length, the input will be taken till the set max_length

- Inputs will be truncated once the set max length is exceeded

- By setting return_tensors="pt", the tokenizer will return the encoded inputs as PyTorch tensors 

- Taking the inputs,output will be generated.

- Num_return_sequences and num_beams - defines the number of outputs required to generate accoridngly (here we will get 20 questions in output) and beam search width

- Tensors will be converted to string again ,conversion will happen in batch and skipping the special characters


