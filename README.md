# Fine-Tuning OpenHermes-2.5 with Direct Preference Optimization (DPO)

This project fine-tunes **OpenHermes-2.5-Mistral-7B** using **Direct Preference Optimization (DPO)**, a more efficient alternative to RLHF for aligning language models.

## 📌 Overview  
Direct Preference Optimization (DPO) is a training technique designed to align language models with human preferences by directly optimizing for preferred responses over rejected ones. Unlike traditional Reinforcement Learning from Human Feedback (RLHF), which relies on reward modeling and policy optimization (such as PPO), DPO simplifies the process by treating preference alignment as a classification task. It utilizes a trained model (policy) and a reference model, ensuring the policy model assigns higher probabilities to preferred responses while reducing the likelihood of rejected ones. This method is computationally efficient, stable, and avoids the complexities of reinforcement learning while still improving response alignment and quality.
## 📝 Dataset  
We use **Intel/orca_dpo_pairs**, a preference dataset where responses are ranked. The dataset is formatted using the **ChatML** template, ensuring proper structuring for DPO training.

## 🔧 Training Process  
1. **Model Selection:** Fine-tuning **OpenHermes-2.5-Mistral-7B**  
2. **Data Formatting:** Using `apply_chat_template()` to structure prompts, preferred, and rejected responses  
3. **LoRA Configuration:** Low-rank adaptation for efficient training  
4. **Quantization:** Reducing memory footprint while maintaining performance  
5. **DPOTrainer:** Automatically handles reference model creation  

## 🚀 Model Name  
```plaintext
teknium/OpenHermes-2.5-Mistral-7B
