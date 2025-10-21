#  PriBan: Privacy-Preserving Text Rewriting in Bangla

> 📝 **Note:**  
> This paper has been **submitted to** [**International Conference on Computer and Information Technology (ICCIT) 2025**](https://iccit.org.bd/2025/about-iccit/) and is **currently under review**.  
> 📦 The **dataset and code** will be released publicly **after acceptance**.

---

##  Overview

**PriBan** is the **first-ever** benchmark dataset and modeling framework for **privacy-preserving sentence rewriting in Bangla (Bengali)**. 

It introduces a **fine-tuned BanglaT5 model** and a **human-inspired dataset** that protect personal or sensitive information while keeping the rewritten text **natural, fluent, and contextually meaningful**.

---

##  Motivation

With the growing use of **Large Language Models (LLMs)**, users often share sensitive information—sometimes unknowingly.  
While there are solid anonymization frameworks for **English**, **Bangla remains a low-resource language** in this area.  

 **PriBan** addresses this gap by:
-  Building the **first Bangla dataset** for privacy-preserving text rewriting.  
-  Fine-tuning **BanglaT5** for two strategies:
    - **Delete** → Fully remove private information.  
    - **Obscure** → Replace sensitive details with generalized, context-aware expressions.  

---

##  Dataset Overview

###  Human-Curated Data
- Translated from the **NAP² (Naturalness and Privacy-Preserving Rewriting)** dataset.  
- Expanded and rewritten manually by **trained Bangla annotators**.  
- Achieved an acceptance rate of **57.25%**, revealing how challenging it is to maintain both **fluency** and **privacy**.

###  LLM-Generated Data
- Synthetic samples generated using **GPT-4**.  
- Two types of generation prompts were used:
  1. 🧩 **Complex, multi-clause sentences** to mimic real-world structures.  
  2. 💬 **Two short connected sentences** with clear personal references.  
- The **human and GPT-4 datasets were combined** to achieve a balanced, rich corpus.  

---

##  Model & Training

###  Models Tested
- 🟢 **BanglaT5** — A monolingual transformer trained on 27.5 GB of Bangla text.  
- 🔵 **mT5** — A multilingual T5 model that includes Bangla among other languages.  

Both models were fine-tuned on **PriBan** for:
- `Delete`: remove sensitive info completely.  
- `Obscure`: replace private details with abstract, context-aware terms.  

---

##  Evaluation Metrics

| 🧾 Metric | 🎯 Description |
|-----------|----------------|
| **Privacy_NLI** | Measures privacy leakage using entailment probability between rewritten text and private info (lower = safer). |
| **ROUGE-1 / ROUGE-Lsum** | Evaluates content preservation and semantic relevance to the original text. |
| **GPT-4 Naturalness Score (1–5)** | Rates fluency and human-likeness of generated rewrites. |

---

##  Results Summary

| 🧠 Model | ✏️ Method | 🔒 Privacy_NLI ↑ | 🧩 ROUGE-1 ↑ | 🧾 ROUGE-Lsum ↑ |
|----------|------------|-----------------|---------------|-----------------|
| **BanglaT5** | Delete | **94.75%** | 69.52% | 69.52% |
| **BanglaT5** | Obscure | **91.43%** | 81.02% | 80.97% |
| **Human** | Delete | 95.28% | 69.93% | 69.66% |
| **Human** | Obscure | 89.49% | 82.20% | 79.76% |

 **Key Insight:**  
BanglaT5 performs *nearly on par with human rewrites* — achieving strong privacy protection while maintaining fluency and readability.

---

##  Key Contributions

✨ **PriBan introduces:**
-  The **first Bangla dataset** for privacy-preserving rewriting.  
-  Two rewriting techniques: **delete** (remove) & **obscure** (generalize).  
-  A **fine-tuned BanglaT5 model** achieving **91–95% privacy accuracy**.  
-  A **hybrid evaluation framework** that measures:
    - Privacy (NLI-based)
    - Semantic utility (ROUGE)
    - Naturalness (GPT-4 scoring)

---

##  Future Work

 Building upon PriBan, future directions include:
-  Expanding the dataset with **more diverse and domain-specific examples** (e.g., medical, legal, financial).    
-  Extending this framework to **other low-resource languages** beyond Bangla.

---
