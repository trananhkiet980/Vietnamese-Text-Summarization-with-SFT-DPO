# 🇻🇳 Vietnamese Text Summarization with SFT & DPO  
**Fine-tuning Qwen / Qwen3-0.6B**

## 📌 Giới thiệu
Repository này thực hiện **fine-tuning mô hình ngôn ngữ Qwen/Qwen3-0.6B cho bài toán tóm tắt văn bản tiếng Việt**, bao gồm hai giai đoạn chính:
- **Supervised Fine-Tuning (SFT)**
- **Direct Preference Optimization (DPO)**

Mục tiêu là so sánh và đánh giá hiệu quả của **DPO so với SFT** trong việc cải thiện chất lượng bản tóm tắt.

---

## 🧠 Mô hình
- **Base model**: `Qwen/Qwen3-0.6B`
- Quy mô nhỏ (~0.6B tham số), phù hợp cho thực nghiệm và fine-tuning trên tài nguyên hạn chế.

---

## 📊 Dữ liệu
- **Dataset**: `OpenHust/vietnamese-summarization`
- **Tập dữ liệu dùng cho DPO**:
```python
from datasets import load_dataset
ds = load_dataset("OpenHust/vietnamese-summarization", split="train[:300]")

## Cấu trúc thư mục
├── SFT.ipynb                  # Supervised Fine-Tuning
├── DPO_new.ipynb              # Direct Preference Optimization
├── testmodel.ipynb            # Thử nghiệm sinh tóm tắt
├── dpo_dataset.csv            # Dữ liệu DPO (chosen / rejected)
├── summarization_results.csv  # Kết quả tóm tắt
├── test.csv                   # Dữ liệu kiểm thử
├── RUNS.txt                   # Ghi chú các lần chạy
├── Report.docx                # Báo cáo
└── Report.pdf                 # Báo cáo (PDF)
