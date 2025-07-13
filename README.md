# 🧠 Loan Approval RAG Q&A Chatbot

This project is a **Retrieval-Augmented Generation (RAG) chatbot** that answers questions based on a loan approval dataset. It combines **document retrieval** with **generative AI** to give intelligent, context-aware responses using a lightweight open-source language model.

---

## 🔗 Dataset

The chatbot uses the publicly available [Loan Approval Prediction Dataset](https://www.kaggle.com/datasets/sonalisingh1411/loan-approval-prediction?select=Training+Dataset.csv) from Kaggle.

---

## 🛠️ Features

- 📄 Loads and processes CSV loan data  
- 📚 Embeds and stores document chunks using `sentence-transformers` + FAISS  
- 🔍 Retrieves relevant chunks based on user query  
- 🤖 Uses `google/flan-t5-base` for generative answers  
- 💬 Fully working chatbot interface inside Google Colab (no API key required)

---

## 📦 Libraries Used

- `pandas` for data handling  
- `sentence-transformers` for embeddings  
- `faiss` for similarity search  
- `transformers` for generative QA model  
- `scikit-learn` (optional) for preprocessing

---

## 💡 How It Works

1. Load and clean the Kaggle CSV dataset.  
2. Split the data into chunks (rows → paragraphs).  
3. Convert chunks to embeddings using `all-MiniLM-L6-v2`.  
4. Index those vectors with FAISS.  
5. Accept a user question.  
6. Retrieve top relevant chunks.  
7. Feed context + question to `flan-t5-base` and generate an answer.

---

## 🚀 Example

```python
question = "What kind of applicants usually get loan approval?"
print(ask_local(question))
```

**Output:**
```
male and female
```

---

## 📁 File Structure

```
loan-approval-rag-chatbot/
│
├── loan_rag_chatbot.ipynb      # Main Colab Notebook
├── requirements.txt            # Python dependencies
├── README.md                   # Project overview
└── Training Dataset.csv        # Input data (upload manually)
```

---

## 📌 Requirements

```bash
pip install pandas faiss-cpu sentence-transformers transformers
```

---

## ✅ Future Improvements

- [ ] Add Gradio/Streamlit chatbot UI  
- [ ] Deploy on Hugging Face Spaces  
- [ ] Fine-tune the model for more accurate answers

---

## 🙋‍♂️ Author

**Ayush**  
Built as part of a practical learning project using Hugging Face, FAISS, and Kaggle.

---

## 🧠 What is RAG?

> RAG = Retrieval-Augmented Generation  
> It retrieves relevant documents before answering, improving accuracy and grounding answers in real data.

---

## 📜 License

This project is open-source and available under the [MIT License](LICENSE).
