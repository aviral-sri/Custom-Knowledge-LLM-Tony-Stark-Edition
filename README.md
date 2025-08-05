# 🧠 Custom Knowledge LLM: Tony Stark Edition

This is a fine-tuned version of the [Qwen2.5-3B-Instruct](https://huggingface.co/Qwen/Qwen2.5-3B-Instruct) large language model, trained specifically to answer questions related to **Tony Stark**, the legendary Marvel character. The project demonstrates how to adapt open-source instruction-tuned LLMs for domain-specific knowledge tasks using efficient fine-tuning methods.

---

## 📌 What It Is

A lightweight, instruction-tuned **knowledge retrieval LLM** that can answer factual, fan-oriented questions about **Tony Stark**. It uses a custom dataset of prompt-completion pairs and adapts the Qwen2.5 model using **PEFT (Parameter-Efficient Fine-Tuning)** with **LoRA (Low-Rank Adaptation)**.

---

## 🎯 Why It Is

This is a **learning + fun project**, aimed at:
- Understanding how to fine-tune LLMs on specific knowledge domains
- Exploring lightweight training using LoRA for limited GPU environments (Colab)
- Showing how fan-based or fictional datasets can help test LLM customization

Though it's themed around Tony Stark, the process used is **reproducible** and applicable to serious production tasks like:
- Domain-specific customer support
- FAQ bots for organizations
- Internal knowledge base assistants

---

## 🛠️ How It Is Built

### ✳️ Model Choice
- **Qwen2.5-3B-Instruct** was selected because:
  - It's small enough to fine-tune on Colab
  - Instruction-tuned already (saves effort)
  - Multilingual and instruction-following by default

### ✳️ Fine-tuning Method
- Used **LoRA via PEFT**, which:
  - Freezes most of the model weights
  - Only trains small adapter layers (RAM/GPU efficient)
  - Works with Hugging Face `Trainer` API

### ✳️ Dataset
- Custom-built JSON with Q&A pairs like:
  - `"Who is Tony Stark?"`
  - `"List of suits developed by Stark"`
  - `"What tech does Iron Man use?"`

---

## 🔁 Can This Be Used for Other Models?

✅ **Yes!**  
The fine-tuning method used (LoRA via PEFT) is **model-agnostic** — you can apply the same code pipeline to:
- LLaMA / Mistral / Falcon / OpenLLaMA
- BERT-style models (with changes for classification)
- Any Hugging Face `AutoModelForCausalLM`-compatible model

Just ensure:
- The model supports text generation
- You choose correct `target_modules` for LoRA
- Tokenizer and dataset are aligned

---

## 📂 What's Inside

- `tonyst.json` — your training dataset
- `train.ipynb` — full training pipeline
- `model.zip` — ready-to-share model
- `tonyst.json` — Custome made dataset

---

## 🧪 Example Usage

```python
from transformers import pipeline

qa = pipeline(
    model="./my_qwen",
    tokenizer="./my_qwen",
    device="cuda"
)

qa("What is Tony Stark’s most advanced suit?")

```

## 🚀 Want a Custom LLM for Your Brand or Domain?

This project is more than a fun fan experiment — it's a **blueprint** for real-world applications.  
With this exact method, you can create tailored AI models for:

🔹 **Startups** building niche AI products  
🔹 **Enterprises** needing internal knowledge assistants  
🔹 **Educators** creating curriculum-aligned AI tutors  
🔹 **Healthcare** teams developing symptom-checker bots  
🔹 **E-commerce** stores launching personalized shopping agents  
🔹 **Legal firms** automating case Q&A from documents  
🔹 Even **fictional universe chatbots** for games, comics, or interactive apps

---

## 🛠️ What I Can Help You Build

✅ Domain-specific LLM (like your brand’s private ChatGPT)  
✅ Fine-tuned Q&A assistant trained on your docs, FAQs, or customer support logs  
✅ Lightweight LoRA fine-tuning without the need for massive GPUs  
✅ Custom pipelines for Hugging Face or local deployment

---

## 📬 Let’s Talk!

Whether you're:
- a **founder** prototyping your first AI MVP,
- a **developer** trying to scale your AI features, or
- a **company** looking to automate knowledge tasks...

**📩 Reach out:** [sriaviralnarain@gmail.com](mailto:sriaviralnarain@gmail.com)  
I'm open to collaborations, consulting, and freelance work.

---

## 💡 Why Trust This Method?

This entire project was built using:
- ⚡ Efficient fine-tuning via **LoRA**
- 🧠 Hugging Face ecosystem for flexibility
- 🔍 Custom data and tokenizer alignment
- 💻 Trained fully on **Google Colab** – no paid GPUs needed

If this worked for Tony Stark’s mind, it can work for **your knowledge base too** 😉


## 🙌 Credits

- **Developer:**  
  [Aviral Srivastava](mailto:sriaviralnarain@gmail.com)  
  [GitHub](http://github.com/aviral-sri) | [LinkedIn](https://www.linkedin.com/in/aviral-srivastava26/)  

- **Base Model:**  
  [Qwen2.5-3B-Instruct](https://huggingface.co/Qwen/Qwen2.5-3B-Instruct) by Alibaba Cloud

- **Libraries & Tools Used:**  
  - [Transformers](https://github.com/huggingface/transformers) by Hugging Face  
  - [Datasets](https://github.com/huggingface/datasets)  
  - [PEFT (LoRA)](https://github.com/huggingface/peft)  
  - [Torch](https://pytorch.org/)  
  - Google Colab (training environment)  
  - [Weights & Biases](https://wandb.ai/) for logging 

- **Inspiration:**  
  Tony Stark / Iron Man (Marvel Universe)  
  This is a non-commercial fan project meant for learning and experimentation.
