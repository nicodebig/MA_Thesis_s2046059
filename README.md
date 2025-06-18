# RESPONSible Service: A Linguistic Analysis of LLMs in Customer Service

This repository accompanies the thesis **"The Role of Large Language Models in Customer Service: A Linguistic Analysis of Synthetically-Generated Customer Service Interactions"** by Nicolò de Bigontina, conducted at Leiden University. The project investigates how large language models (LLMs), specifically GPT-4o, express and differentiate between four key communication styles in customer service: **clarity, friendliness, empathy, and politeness**.

## 📁 Repository Structure

```
.
├── THESIS_CODE.ipynb                # Main analysis notebook
├── concreteness_scores.txt          # Word-level concreteness values
├── NGSL_1000.txt                    # First 1000 words from NGSL
├── NGSL_2000.txt                    # Second 1000 words from NGSL
├── requirements_1.txt               # Package requirements (subset 1)
├── requirements_2.txt               # Package requirements (subset 2)
├── requirements_3.txt               # Package requirements (subset 3)
├── requirements_nlp.txt             # NLP-specific requirements
└── RESPONSible Service/             # Main dataset folder
    ├── dataset_clear.parquet        # CS responses with clarity style
    ├── dataset_friendly.parquet     # CS responses with friendly style
    ├── dataset_empathetic.parquet   # CS responses with empathetic style
    ├── dataset_polite.parquet       # CS responses with polite style
```

## 📝 Thesis Overview

The study introduces the **RESPONSible Service Dataset**, a synthetic corpus of 4,000 GPT-4o-generated customer service interactions, each labeled and styled according to one of the four communication modes. It includes:

- Detailed **linguistic profiling** using metrics such as cohesion, sentiment, deixis, formality, and concreteness.
- Evaluation of model performance on stylistic generation using in-context learning, supervised fine-tuning, and direct preference optimization.
- Comparison of outputs using BERTScore and ROUGE-L.

Key findings include:
- **High human agreement** for friendliness, empathy, and politeness subsets.
- **Clarity** emerged as the most unpredictable and challenging style to model.
- **In-context learning** outperformed other training methods in generating stylistically appropriate responses.

## 📊 Usage

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/responsible-service.git
   cd responsible-service
   ```

2. **Install dependencies**:

   > ⚠️ Dependencies are split across multiple files for modularity, and **some contain conflicting versions of the same packages**.  
   > **Only install the requirements file(s) corresponding to the module(s) you intend to run.**

   Use one of the following based on the part of the notebook you're working with:

   - `requirements_1.txt` — for **Text Generation Tasks using ICL and DPO**
   - `requirements_2.txt` — for **Text Generation Tasks using SFT**
   - `requirements_3.txt` — for **Dataset Generation** and **Text Generation Overlap Metrics**
   - `requirements_nlp.txt` — for **Linguistic Data Profiling**

   For example, to run the linguistic profiling section:
   ```bash
   pip install -r requirements_nlp.txt
   ```

3. **Open and run the Jupyter notebook**:
   ```bash
   jupyter notebook THESIS_CODE.ipynb
   ```

> ✅ **Tip**: If you plan to run multiple modules with conflicting dependencies, consider using virtual environments or tools like `venv` or `conda` to isolate them.

## 📂 Dataset: RESPONSible Service

Each `.parquet` file contains 1,000 customer service interactions focusing on one communication style. Each item has three fields:

- `request`: Customer query.
- `response0`: Initial LLM-generated reply reflecting the target style.
- `response1`: A more stylistically marked version of `response0`.

## 📄 License and Ethics

- All data were **synthetically generated** using GPT-4o.
- The generated data are in English.
- No real customer data was used.
- The project complies with ethical standards for computational linguistics research.

## 📬 Contact

For questions or collaboration inquiries, please contact:

**Nicolò de Bigontina**  
[Email](mailto:n.de.bigontina@umail.leidenuniv.nl)  
Leiden University, LUCL
