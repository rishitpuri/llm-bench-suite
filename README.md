# **LLM Benchmarking Suite for Clinical Trial Eligibility Matching**

This repository contains a **scalable and optimized pipeline** for evaluating patient eligibility for clinical trials using **LLMs**. The pipeline leverages **PyTorch, Hugging Face, and optimized batch processing** to enhance inference speed and memory efficiency.

---

## **🚀 Features**
- **Patient-Trial Matching**: Compares patient notes with clinical trial criteria to determine eligibility.
- **Optimized LLM Inference**: Implements **batch processing, memory-efficient execution, and GPU acceleration** using **PyTorch**.
- **Custom Prompt Engineering**: Uses **structured prompt templates** to guide LLMs for accurate JSON-based reasoning.
- **Multi-Model Evaluation**: Benchmarks different models like **DeepSeek R1, LLAMA 8B, and GPT-based models**.
- **Flexible Data Processing**: Supports structured and unstructured datasets (NIH datasets, SIGIR trials, etc.). Reach out for more details.
- **Scalable Deployment**: Future-ready architecture to integrate **Docker and cloud-based inference**.

---

## **📁 Project Structure**
```
📦 clinical-trial-pipeline
│── 📂 Dataset/                                   # Input datasets (patient notes, trials, SIGIR data)
│── 📄 llm_benchmarking_suite.ipynb               # Main pipeline notebook
│── 📄 eligibility_matching_results_unquant.json  # json output
│── 📄 eligibility_matching_results_unquant.tsv   # tsv conversion output 
│── 📄 misclassified_results.tsv                  # misclassified prediction output
│── 📄 requirements.txt                           # Dependencies
│── 📄 README.md                                  # Project documentation
│── 📄 LICENSE                                    # Project License
```

---

## **📌 Setup & Installation**
### **1️⃣ Clone the Repository**
```bash
git clone https://github.com/adityapadgal/llm-benchmarking-suite.git
cd llm-benchmarking-suite
```

### **2️⃣ Install Dependencies**
```bash
pip install -r requirements.txt
```

### **3️⃣ Download Models (Hugging Face)**
```python
from transformers import AutoModelForCausalLM, AutoTokenizer

model_name = "deepseek-ai/DeepSeek-R1-Distill-Llama-8B"
tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForCausalLM.from_pretrained(model_name, torch_dtype=torch.float16, device_map="auto")
```

---

## **🛠️ Usage**
### **1️⃣ Running the Pipeline**
Run the Jupyter Notebook for evaluation:
```bash
jupyter notebook llm_benchmarking_suite.ipynb
```

### **2️⃣ Process Your Own Dataset**
Modify `Dataset/` folder and update **llm_benchmarking_suite.ipynb**:
```ipynb
batch_size: 4
model_name: "deepseek-ai/DeepSeek-R1-Distill-Llama-8B"
max_tokens: 1024
```

---

## **📊 Benchmark Results**
| Model              | Accuracy (%) | JSON Adherence (%) | Inference Time (minutes) |
|--------------------|-------------|--------------------|--------------------------|
| GPT-4             | 87%         | 98%                | -                 |
| DeepSeek R1 8B    | 63%         | 100%                | 75 mins (post-optimization) |
| LLAMA 8B          | 80%         | 92%                | 105 mins                  |
| LLAMA 3B          | 22%         | 50%                | 130 mins                  |

**Optimization Outcome:**
- **Reduced inference time from 5-6 hours to 1 hour 15 mins** by implementing **batch processing with PyTorch**.
- **Enhanced JSON output consistency** by refining prompt structures.
- **Memory-efficient execution** using **TensorRT and Hugging Face Accelerate**.

---

## **🚀 Future Work**
- **Fine-tuning models** for better eligibility reasoning.
- **Deploying via FastAPI** for real-time clinical trial matching.
- **Exploring quantized models** for mobile-friendly deployment.

---

## **📜 Citation**
If you find this work useful, please consider citing:
```
@misc{clinical_trial_pipeline_2025,
  author = {Aditya Padgal},
  title = {LLM Benchmarking Suite},
  year = {2025},
  url = {https://github.com/adityapadgal/llm-benchmarking-suite}
}
```

---

## **🤝 Contributions**
Contributions are welcome! Feel free to open an issue or submit a pull request.

---

## **📬 Contact**
For questions, reach out via [adityapadgal@gmail.com](mailto:adityapadgal@gmail.com) or open an issue.
