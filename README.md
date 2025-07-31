# 📘 A/B Testing of Fine-Tuned QLoRA Bible Model

This repository is a **continuation** of my previous project, where I fine-tuned a QLoRA-based language model on a custom Biblical dataset.

The original model and full fine-tuning guide are available here:  
🔗 [Bible_Qlora_Model](https://github.com/boomshineking/Bible_Qlora_Model)

---

## 🧪 Objective: A/B Testing - Quantized vs Full-Precision Inference

After successfully creating and quantizing the model, I wanted to evaluate the difference between:
- A model loaded in **full precision**
- The same model loaded with **4-bit quantization**

> Due to hardware limitations (16GB VRAM), all test prompts are limited to a maximum of **500 tokens**.

---

## 🧠 Model Configuration

| Model | Precision | Loader     |
|-------|-----------|------------|
| A     | Full (FP16/FP32) | `AutoModelForCausalLM` (default) |
| B     | 4-bit Quantized  | `bitsandbytes` + QLoRA           |

Both models share the **same fine-tuned weights** and architecture. The only difference is in how they are loaded and used at inference time.

---

## 📸 Screenshots
<img width="1818" height="915" alt="abtest1" src="https://github.com/user-attachments/assets/c50feab2-9654-4c0f-91d0-ab3c3229aa69" />
<img width="850" height="870" alt="abtest2" src="https://github.com/user-attachments/assets/2606a9be-cbb7-4731-a758-fa283b84e1d3" />

## 📎 References

- Original fine-tuned model: [Bible_Qlora_Model](https://github.com/boomshineking/Bible_Qlora_Model)
- Quantization via [QLoRA Paper](https://arxiv.org/abs/2305.14314)
- Quantized loading with [bitsandbytes](https://github.com/TimDettmers/bitsandbytes)

---

## ⚙️ Setup Instructions (Optional)

To run the A/B testing script locally:

```bash
git clone https://github.com/yourusername/Bible_Qlora_AB_Test.git
cd Bible_Qlora_AB_Test
pip install -r requirements.txt
python ab_test.py
