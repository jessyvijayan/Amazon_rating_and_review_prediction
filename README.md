# Amazon_rating_and_review_prediction

Amazon Product Review Classifier: Multi-Category NLP Engine
This project implements an end-to-end NLP pipeline to classify unstructured Amazon product reviews into five distinct categories: Beauty, Grocery, Home & Kitchen, Office Products, and Pet Supplies. The system uses Deep Learning (LSTM) to understand the semantic context of consumer feedback across 250,000+ records.

🚀 Key Features
High-Scale Data Parsing: Engineered a custom gzip parsing and unzipping utility to efficiently process and merge multiple large-scale Amazon metadata files into a unified dataset.
Multi-Class Classification: Developed a model to differentiate between 5 product domains by concatenating reviewText and summary fields for richer semantic input.
Automated NLP Pipeline: Implemented a robust text cleaning workflow including Regex-based noise removal and NLTK-driven stop-word filtering.
Sequence Modeling: Utilized Keras Tokenizer and pad_sequences to transform variable-length text reviews into uniform numerical tensors for deep learning.
🛠️ Tech Stack
Core NLP: NLTK (Stop-words, Regex processing)
Deep Learning: TensorFlow / Keras (Sequential API)
Data Engineering: Python gzip module, Pandas, NumPy
Feature Extraction: Keras Preprocessing (Tokenization & Padding)

📊 Data Preparation & Engineering
Extraction: Leveraged a generator-based parsing function to handle large binary JSON files without memory overflow.
Dataset Balancing: Sampled ~53,000 reviews from each of the 5 categories to create a balanced dataset of 266,000+ entries, preventing model bias.
Feature Synthesis: Created a composite text feature by merging review bodies with summaries to capture both detailed feedback and concise sentiment.
Cleaning: Removed non-alphabetic characters and filtered out English stop-words to focus the model on category-specific keywords.

💻 Model Architecture (Planned/Implemented)
The model follows a Sequential flow:
Embedding Layer: To map high-dimensional text data into dense vectors.
LSTM Layer: To capture long-term dependencies and technical jargon unique to specific product categories (e.g., "moisturizer" vs. "stapler").
Dense Output Layer: A Softmax-activated layer to predict the probability across the 5 categories.

💻 How to Run
Clone the repository:
git clone [git@github.com:jessyvijayan/Amazon_rating_and_review_prediction.git]

Install Dependencies:
pip install tensorflow pandas nltk numpy

Run Analysis:
python amazon_category_classifier.py
Use code with caution.
