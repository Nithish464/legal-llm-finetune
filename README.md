# Legal LLM Fine-tuning with QLoRA

> Converted a general-purpose LLM into a domain-specific legal reasoning system using QLoRA — training only 0.57% of 7B parameters on a free Google Colab T4 GPU.

---

## 🚀 Key Result

| Metric | V1 (10 examples) | V2 (60 examples) |
|--------|-----------------|------------------|
| Coherence | ~0% | ~85% |
| Hallucination rate | ~95% | ~20% |
| Legal accuracy | ~5% | ~75% |
| Structured output | ~0% | ~90% |

---

## 🔍 Before vs After

**Q: What is anticipatory breach of contract?**

**Base Model (no fine-tuning):**  
Generic explanation without legal structure

**V1 (10 examples — overfitted):**  
Anti. #10 A A A A A A A A A A A A A A

**V2 (60 examples — improved):**  
Anticipatory Breach occurs when one party to a contract indicates that they will not perform their obligations. The other party may terminate immediately or wait for actual non-performance. Damages are available in either case. ✅

---

## 🧠 Approach

- Base model: Mistral-7B
- Method: QLoRA (4-bit quantization)
- LoRA rank: 16
- Trainable params: 42M / 7B (0.57%)
- GPU: Google Colab T4 (Free)

---

## 📊 Training Comparison

| Parameter | V1 | V2 |
|-----------|----|----|
| Training examples | 10 | 60 |
| Epochs | 3 | 2 |
| repetition_penalty | No | 1.3 |
| Outcome | Overfit | Stable & coherent |

---

## 🔗 Models (Hugging Face)

- V1 (baseline): https://huggingface.co/Nithish04/legal-mistral-7b-qlora  
- V2 (improved): https://huggingface.co/Nithish04/legal-mistral-7b-qlora-v2  

---

## 💡 Key Learnings

- Small datasets cause severe overfitting in LLMs  
- Data scaling (10 → 60 examples) significantly improves output quality  
- QLoRA enables efficient fine-tuning under limited compute  
- Training only 0.57% of parameters can still achieve strong domain adaptation  
- Output control techniques (like repetition_penalty) improve coherence  

---

## 📚 Domain Coverage

- Anticipatory Breach  
- Promissory Estoppel  
- Rights of Unpaid Seller  
- Free Consent & Coercion  
- Consideration  
- Law of Agency  
- Doctrine of Frustration  
- Minor Contracts  
- Offer and Acceptance  

---

## ⚙️ How to Run

1. Open notebook in Google Colab  
2. Enable GPU (Runtime → T4)  
3. Add Hugging Face token  
4. Run all cells  

---

## 🎯 Summary

This project demonstrates how a general LLM can be transformed into a domain-specific expert under strict compute constraints using parameter-efficient fine-tuning.
