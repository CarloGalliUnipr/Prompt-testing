LLM-Assisted Screening for Systematic Reviews
This repository demonstrates how to use OpenAI’s GPT-3.5-Turbo model to automate part of the abstract-screening process in systematic reviews. Two prompting strategies—“soft” vs. “strict”—are illustrated using a fictional dataset of ten abstracts about a hypothetical antihypertensive drug (“Drug X”).

Overview
Ten Fictional Abstracts

Each abstract has a title and body, simulating typical PubMed entries.
Some abstracts match the inclusion criteria (adult population, mentions of Drug X, randomized design, ≥6-month follow-up), while others clearly violate them.
Prompts

Soft Prompt: Accept the study unless there is a clear violation (pediatric, short follow-up, non-randomized, etc.).
Strict Prompt: Require explicit mention of each inclusion criterion, rejecting if anything is absent.

Evaluation
The script compares GPT’s predictions against manually assigned ground truth labels.
A confusion matrix and performance metrics (Accuracy, Precision, Recall, F1 Score) are computed for each prompt.

File Contents
Prompt_examples.ipynb

The script does:
Defines fictional abstracts and their ground truth labels.
Sets up two prompts (soft and strict).
Calls GPT-3.5-Turbo for each abstract using each prompt.
Stores the model’s “ACCEPT”/“REJECT” predictions.
Computes and prints out confusion matrices plus accuracy, precision, recall, and F1 scores.
README.md
This file, describing the purpose of the repository and usage instructions.

Requirements:
Python 3.7+
Packages:
openai (for calling GPT-3.5-Turbo)
sklearn (for confusion matrix and performance metrics)
You can install dependencies via:
pip install openai scikit-learn
OpenAI API Key
Sign up at OpenAI to obtain an API key.
Store your key securely and never commit it directly to a public repository.

How to Use:
Clone or Download this repository.
Open Prompt_examples.ipynb in Google Colab (preferred).

Set the OpenAI API Key:
Replace YOUR_API_KEY with your actual API key from OpenAI.

Run the script

Observe the classification results in the console output:
Predictions: A list of “ACCEPT” or “REJECT” for each abstract under both prompting strategies.

Confusion Matrix: How many abstracts were correctly vs. incorrectly classified.
Accuracy, Precision, Recall, and F1: Key performance metrics illustrating the trade-offs between a lenient (soft) and a stringent (strict) approach.

Contributing:
This example is provided for educational purposes. If you have suggestions for improvements, feel free to open an issue or submit a pull request.

License
This project is licensed under the MIT License. Feel free to adapt it to your use cases, but remember to comply with any license agreements for third-party services or libraries.
