# **Text Summarizer with Attention Mechanism**  

## **Project Overview**  
This project implements a **Text Summarization** model using **Sequence-to-Sequence (Seq2Seq) architecture** with an **Attention mechanism**. The model is trained on the **Samsum Dataset**, which contains dialogue-based conversations and their summaries. The attention mechanism helps the model focus on relevant parts of the input text while generating summaries, leading to improved accuracy.  

## **Dataset**  
- **Samsum Dataset** (Available on Kaggle)  
- It consists of dialogues along with human-written summaries.  

## **Features**  
- **Preprocessing Steps**:  
  - Lowercasing  
  - Removing HTML tags, URLs, and emojis  
  - Expanding contractions (e.g., *don’t → do not*)  
  - Replacing chat abbreviations (e.g., *LOL → Laughing Out Loud*)  
  - Tokenization and sequence padding  

- **Model Architecture**:  
  - **Encoder**: Bi-directional LSTM  
  - **Decoder**: LSTM with Attention Mechanism  
  - **Attention Layer**: Helps model focus on key parts of input text  
  - **Embedding Layer**: Word representation  
  - **Final Dense Layer**: Softmax activation for word prediction  

- **Training**:  
  - Optimizer: **Adam**  
  - Loss Function: **Sparse Categorical Crossentropy**  
  - Metrics: **Accuracy**  
  - Early Stopping & Model Checkpointing  

- **Evaluation**:  
  - **BLEU Score**: Measures the quality of generated summaries  
  - **Visualization**: Loss and accuracy graphs  

## **Installation & Requirements**  
### **1. Clone the repository**  
```sh
git clone https://github.com/your-repo/text-summarizer-attention.git
cd text-summarizer-attention
```
### **2. Install dependencies**  
```sh
pip install -r requirements.txt
```
### **3. Download Dataset**  
```sh
kaggle datasets download -d nileshmalode1/samsum-dataset-text-summarization
unzip samsum-dataset-text-summarization.zip
```
### **4. Run Training**  
```sh
python train.py
```
### **5. Run Prediction on Custom Input**  
```python
from model import summarize_user_input

user_text = "Your long text here..."
summary = summarize_user_input(user_text, tok, model, max_length_combined)
print("Generated Summary:", summary)
```

## **Results**  
- The model effectively generates concise summaries of dialogues.  
- Achieved a **BLEU Score** of **68.35** (replace with actual score).  
