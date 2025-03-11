# Blog Generator - Llama Local API

This project is a **Blog Generator** powered by a **locally hosted Llama model** using **LangChain** and **Streamlit**. The API enables users to generate high-quality blog content efficiently.

## Features
✅ Generate blog posts using AI
✅ Locally hosted Llama model for privacy
✅ API-based interaction for automation
✅ Streamlit UI for easy blog generation

## Requirements
Ensure you have the following installed:
- Python (>=3.8)
- Llama model (local)
- Required Python dependencies

## Installation

### 1️⃣ **Clone the Repository**
```bash
git clone <repository-url>
cd <repository-folder>
```

### 2️⃣ **Install Dependencies**
```bash
pip install -r requirements.txt
```

### 3️⃣ **Set Up Local Llama Model**
This project requires a locally hosted **Llama model** using **ctransformers**.

#### 🔹 **Download the Model**
Download a compatible model from [TheBloke's Hugging Face](https://huggingface.co/TheBloke) or another source.

Example command:
```bash
mkdir models
wget -P models/ <model-download-link>
```

#### 🔹 **Load the Model in Python**
Modify `app.py` to load your local Llama model:
```python
from ctransformers import CTransformers

llm = CTransformers(model='models/llama-2-7b-chat.ggmlv3.q8_0.bin',
                    model_type='llama',
                    config={'max_new_tokens': 256, 'temperature': 0.01})
```

{
    "response": "AI has been advancing rapidly, transforming industries..."
}
```

## Running the Streamlit App
To run the **Streamlit UI**, use:
```bash
streamlit run app.py
```

This will open a local UI where you can enter blog topics and generate content.

## Using `app.py` for Blog Generation
The `app.py` script includes a function that generates blog content using a locally hosted **Llama 2 model**.

### Function: `getLLamaresponse()`
This function takes in three parameters:
- **`input_text`** – The topic of the blog
- **`no_words`** – The desired word count
- **`blog_style`** – The writing style of the blog

#### Example Usage:
```python
response = getLLamaresponse("AI in Healthcare", 500, "technical")
print(response)
```

The function uses **LangChain** to format a prompt and interacts with the **Llama 2 model** stored in `models/llama-2-7b-chat.ggmlv3.q8_0.bin`.

## Summary
✅ **Generate AI-powered blogs locally**
✅ **Secure and private** (no cloud API required)
✅ **User-friendly UI with Streamlit**

---

Author: Chirag S Shetty

