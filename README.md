# BERT-Based Named Entity Recognition (NER) Model
https://github.com/Avnish2004/nert_bert.git<br>
## Overview<br>
This project uses a pre-trained BERT model for Named Entity Recognition (NER) tasks. The model is fine-tuned on custom data for token classification. It identifies entities in text sequences based on the labels provided in the training data. <br>
## Table of Contents
* Prerequisites
* Installation
* Excel to JSON Converter
* Fine Tuning the Model
* Making Predictions
* Model Architecture<br>
## Prerequisites
* Python 3.7 or higher
* PyTorch
* Transformers library by Hugging Face
* tqdm for progress bars <br>
## Installation
To set up the environment, clone this repository and install the necessary Python packages:
git clone https://github.com/Avnish2004/nert_bert.git<br>
cd <repository_directory> <br>
pip install -r requirements.txt <br>

## Excel to JSON Converter
Prepare your Excel file with the necessary columns: Discharge Summary and entities.<br>
The script reads the data from the Excel file and processes each row to extract and format entities into a structured JSON format.<br>
Download the json data file.

## Fine Tuning Model
Load your dataset: Place your dataset in a JSON file. Each entry should contain the text and corresponding entities. The entities should have a start, end, and label.<br>
Example data format:

json
Copy code
[
    {
        "text": "symptoms of acute myocardial infarction.",
        "entities": [
            {
                "start": 14,
                "end": 35,
                "label": "Disease"
            }
        ]
    }
]

## Model Architecture
The model is based on BERT (Bidirectional Encoder Representations from Transformers) for token classification. It has been fine-tuned to identify specific entities in a sequence of text.

## Fine Tuning Process
Freezing Layers: All BERT layers except the classification head are frozen during training to focus on fine-tuning the task-specific layer.<br>
Batch Size: Training is performed with a batch size of 16.<br>
Learning Rate: The learning rate is set to 2e-5.<br>
Epochs: The model is trained for 5 epochs.<br>

## Making Predictions
Load the trained model and tokenizer that has been added.<br>
At last place your input text and make predictions.



