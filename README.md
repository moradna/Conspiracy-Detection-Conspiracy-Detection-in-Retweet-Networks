# Conspiracy-Detection-Conspiracy-Detection-in-Retweet-Networks
Enhancing Conspiracy Detection in Hebrew Tweets Using Retweet Networks and Large Language Models
# Conspiracy Detection in Hebrew Tweets with LLMs and Network Context

This project explores enhanced conspiracy theory detection in Hebrew-language tweets using a combination of **textual analysis via large language models (LLMs)** and **retweet network-based features**. The work focuses on identifying hidden conspiratorial content—particularly in the context of COVID-19 and vaccine skepticism—by combining **graph structure insights** with **Chain-of-Thought (CoT) prompting** for better reasoning.

## 📌 Project Goals

- Detect conspiratorial tweets in Hebrew using LLMs.
- Integrate **social network context** (retweets, user connections) into model inputs.
- Leverage **Chain-of-Thought reasoning** to improve model interpretability and accuracy.
- Evaluate performance across different structured prompting strategies.

## 🧠 Methodology

1. **Dataset**  
   - 4,000 Hebrew tweets labeled as:  
     - `Unrelated`  
     - `COVID-related`  
     - `Vaccine Opposition`  
   - Annotated using 5 binary questions regarding conspiracy traits.

2. **Graph Construction**  
   - Built a **retweet network** (195 users, 739 edges).  
   - Extracted key **network features** per user:
     - In/Out degree
     - Betweenness and closeness centrality
     - Community size
     - Number of conspiratorial neighbors

3. **Prompting Strategies**  
   - Created 7 prompt types:
     - Minimal prompt (text only)
     - Prompts with added network features (degree, centrality, etc.)
     - Full-feature prompt with and without Chain-of-Thought (CoT)

## 🧪 Results

| Prompt Type                         | Accuracy (%) | Precision (%) | Recall (%) | F1 Score (%) |
|------------------------------------|--------------|----------------|-------------|----------------|
| Minimal Prompt                     | 59.29        | 41.11          | 94.39       | 57.28          |
| Degree-Based Prompt                | 62.97        | 43.33          | 95.29       | 59.57          |
| Centrality-Based Prompt            | 69.36        | 47.68          | 81.05       | 60.04          |
| Community + Neighbors-Based Prompt| 58.54        | 40.76          | 93.37       | 56.74          |
| Full-Feature Prompt                | 59.52        | 41.69          | 91.96       | 57.37          |
| Minimal Prompt + CoT               | 57.85        | 40.58          | 94.69       | 56.81          |
| **Full-Feature Prompt + CoT**      | **76.04**    | **58.12**      | **68.34**   | **62.82**      |

> The **Full-Feature Prompt with CoT** outperformed all other strategies, demonstrating that LLMs can better interpret network-based context when guided step-by-step.

## 📈 Key Insights

- **Text-only approaches** yielded poor precision (many false positives).
- **Network features** help provide valuable context for tweet classification.
- **Chain-of-Thought** prompting enables the model to reason more effectively about complex feature combinations.

## 🛠️ Technologies

- Hebrew LLMs: `DictaLM-2.0`, `Gemini`
- Graph tools: NetworkX
- Prompting + Evaluation: Python

## 📂 Project Structure

