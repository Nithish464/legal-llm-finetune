# Legal LLM Fine-tuning with QLoRA

Fine-tuned Mistral-7B on Indian Legal domain using QLoRA.
Trained only 0.57% of 7B parameters on free Google Colab T4 GPU.

## Models on HuggingFace
- V1 baseline: https://huggingface.co/Nithish04/legal-mistral-7b-qlora
- V2 improved: https://huggingface.co/Nithish04/legal-mistral-7b-qlora-v2

## V1 vs V2 Results

| Metric | V1 (10 examples) | V2 (60 examples) |
|--------|-----------------|------------------|
| Coherence | 0% | 85% |
| Hallucination rate | 95% | 20% |
| Legal accuracy | 5% | 75% |
| Structured output | 0% | 90% |

## Real Output Comparison

Q: What is anticipatory breach of contract?

V1: Anti. #10 A A A A A A A A A A A A A A A A A A A A

V2: Anticipatory Breach occurs when one party to a contract
indicates that they will not perform their obligations.
The other party may terminate immediately or wait for
actual non-performance. Damages are available in either case.

## Tech Stack
- Mistral-7B-v0.1
- QLoRA 4-bit quantization
- LoRA rank 16 — only 0.57% params trained (42M of 7B)
- Google Colab T4 GPU (Free)
- HuggingFace PEFT + TRL

## Training Details

| Parameter | Value |
|-----------|-------|
| Base model | Mistral-7B-v0.1 |
| Method | QLoRA 4-bit |
| LoRA rank | 16 |
| Trainable params | 42M / 7B (0.57%) |
| Epochs | 2 |
| GPU | Colab T4 Free |
| Domain | Indian Contract Law |

## How to Run
1. Open `legal_qlora_training.ipynb` in Google Colab
2. Runtime → Change runtime type → T4 GPU
3. Add your HuggingFace token in Cell 4
4. Runtime → Run all

## Topics Covered
- Anticipatory Breach of Contract
- Promissory Estoppel
- Rights of Unpaid Seller
- Free Consent
- Consideration
- Law of Agency
- Doctrine of Frustration
- Minor Contracts
- Offer and Acceptance
