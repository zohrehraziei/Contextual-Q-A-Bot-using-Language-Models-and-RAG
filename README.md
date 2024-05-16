# Contextual Q&A Bot using Language Models and RAG

This project demonstrates the implementation of a contextual Q&A bot that utilizes open-source language models (LLMs) and retrieval-augmented generation (RAG) to answer questions based on the content of a provided PDF document. The bot preprocesses the PDF content, develops a context-aware Q&A system, and implements a mechanism to determine if a question is in or out of context, denying out-of-context questions.

## Features

- Reads and preprocesses the content of a provided PDF document
- Develops a Q&A bot using open-source LLMs to answer questions based on the PDF's content
- Implements a mechanism to determine if a question is in or out of context and denies out-of-context questions
- Optimizes the program for efficiency and scalability, considering large volumes of data

## Prerequisites

To run this project, you need the following dependencies:

- Python 3.x
- PyTorch
- Transformers
- Langchain
- FAISS
- Sentence Transformers
- PyPDF2

You can install the required packages using the following command:

```
pip install -q -U torch tensorflow transformers langchain faiss-cpu sentence_transformers
pip install -q peft==0.4.0 trl==0.4.7 accelerate==0.21.0 bitsandbytes==0.41.3
pip install pypdf PyPDF2
```

## Usage

1. Clone the repository

2. Prepare your PDF document and place it in the project directory.

3. Open the Jupyter Notebook `Contextual_Q&A_Bot_Langchain_RAG.ipynb` and run the cells in sequential order.

4. When prompted, enter the file name of your PDF document.

5. The program will preprocess the PDF content, develop the Q&A bot, and allow you to ask questions based on the PDF's content.

6. The bot will provide answers to your questions, taking into account the context of the PDF content.

7. If a question is determined to be out of context, the bot will deny answering it.

## Example

Here's an example of how to use the contextual Q&A bot:

1. Place your PDF document, e.g., `example.pdf`, in the project directory.

2. Open the `Contextual_Q&A_Bot_Langchain_RAG.ipynb` notebook and run the cells.

3. When prompted, enter the file name `example.pdf`.

4. The program will preprocess the PDF content and develop the Q&A bot.

5. You can now ask questions based on the PDF's content. For example:

   - Question: What is the main topic of the document?
     Answer: The main topic of the document is [main topic extracted from the PDF].

   - Question: Please explain the concept of [concept mentioned in the PDF].
     Answer: [Explanation of the concept based on the PDF's content].

   - Question: What is the capital of France?
     Answer: The question is out of context. I cannot provide an answer based on the given document.

6. The bot will provide answers to your questions, considering the context of the PDF content, and deny out-of-context questions.

## Optimization and Scalability

The program is optimized for efficiency and scalability to handle large volumes of data. The following optimizations are implemented:

- The PDF content is preprocessed using Langchain's text splitter to split the content into manageable chunks, considering the context limit of the LLM.
- The preprocessed content is vectorized using a pre-trained embedding model (MiniLM) for efficient retrieval.
- The program utilizes an open-source LLM (Mistral 7b) with a 32-bit configuration for memory efficiency.
- The Q&A bot is developed using retrieval-augmented generation (RAG) to retrieve relevant context and provide context-aware responses.
