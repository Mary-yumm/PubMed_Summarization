# PubMed Article Summarization Application Documentation

This documentation provides a comprehensive guide to the PubMed Article Summarization application, detailing the entire process from data exploration to model selection and web application development. The instructions for running the application and any additional setup required are also included.

## Table of Contents

1. [Introduction](#introduction)
2. [Data Exploration](#data-exploration)
3. [Model Selection](#model-selection)
4. [Application Development](#application-development)
5. [Running the Application](#running-the-application)
6. [Additional Setup](#additional-setup)
7. [Code Explanation](#code-explanation)
   - [Helper Functions](#helper-functions)
   - [Summarization Function](#summarization-function)
   - [ROUGE Score Calculation](#rouge-score-calculation)
   - [ROUGE Score Plotting](#rouge-score-plotting)
   - [Streamlit App Code](#streamlit-app-code)

## Introduction

The PubMed Article Summarization application is designed to help users summarize PubMed articles using a pre-trained Hugging Face model. The application provides a web interface for users to input text or upload a file containing the article. The summarized text is then displayed along with ROUGE scores to evaluate the quality of the summary.

## Data Exploration

Before building the application, it's essential to understand the nature of PubMed articles, which are typically rich in scientific terminology and structured in a formal format. This understanding helps in preprocessing the text effectively for summarization.

## Model Selection

The application uses the Hugging Face `facebook/bart-large-cnn` model for summarization. This model is selected for its effectiveness in generating coherent and contextually relevant summaries. The model is accessed through the `transformers` library, which provides an easy-to-use pipeline for summarization tasks.

## Application Development

The application is developed using Streamlit, a popular framework for building interactive web applications in Python. The following components are included in the development process:

- **User Interface**: Allows users to input text or upload a file.
- **Text Preprocessing**: Minimal cleaning to ensure the text is suitable for summarization.
- **Summarization**: Uses the selected model to generate a summary.
- **ROUGE Score Calculation**: Evaluates the summary using ROUGE metrics.
- **Visualization**: Displays ROUGE scores in a bar chart.

## Running the Application

To run the application, follow these steps:

1. Ensure you have Python installed (preferably version 3.7 or higher).
2. Install the required libraries:
   ```bash
   pip install streamlit transformers nltk rouge-score matplotlib

3. Save the application code in a file, for example, app.py.
Run the application using Streamlit
    ```bash
    streamlit run app.py
## NLTK Data
The application uses the NLTK library for tokenization.

## Code Explanation
### Helper Functions
- **Store_capitalization**: 
Stores the positions of capitalized words in the original text.
- **Restore_capitalization**: Restores capitalization in the summary based on the stored positions.
- **Clean_text**: Performs minimal text cleaning by lowercasing and removing extra whitespace.

### Summarization Function
- **Summarize**: Summarizes the article text using the Hugging Face model. It also restores capitalization and adjusts summary length based on user selection.
### ROUGE Score Calculation
- **Calculate_rouge_scores**: Calculates ROUGE scores (ROUGE-1, ROUGE-2, and ROUGE-L) between the reference and generated summary using the rouge_score library.
### ROUGE Score Plotting
- **Plot_rouge_scores**: Plots the ROUGE scores using Matplotlib and displays the chart in the Streamlit app.

### Streamlit App Code
The Streamlit app code includes:
- **Title and Introduction**: Provides an overview of the application.
- **User Input/Upload Selection**: Allows users to either enter text manually or upload a file.
- **Summary Length/Style Selection**: Lets users choose the length/style of the summary.
- **Button to Summarize and Display Results**: Summarizes the text, displays the original and summarized text, calculates ROUGE scores, and plots them.