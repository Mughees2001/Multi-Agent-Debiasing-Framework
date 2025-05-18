# Multi-Agent Debiasing Framework with Online Search Based-Validation

<div align="center">
Mughees Ur Rehman (mughees@vt.edu), Ayush Roy (ayushroy24@vt.edu)
</div>

## Abstract

Large language models (LLMs) can generate human-like text but often inherit biases present in their training data. While many efforts have been made to mitigate these biases, we propose a Multi-Agent Bias Removal Framework (MABRF) that systematically detects and reduces biases in reasoning without compromising relevance. Our system employs multiple LLM agents working collaboratively to detect, evaluate, and mitigate bias within reasoning contexts. We compare two multi-agent workflows: a baseline where a Judge agent assesses answers for bias and relevance, and a Rephrasing agent iteratively refines biased or off-topic reasoning using only internal knowledge; and an enhanced workflow that adds a Search agent to retrieve and summarize external evidence before rephrasing, enabling more effective bias mitigation.

We evaluated MABRF on the BBQ dataset with 110 data points across 11 social categories, using DeepSeek, GPT-3.5-Turbo, GPT-4, and Claude-3-Haiku. The baseline pipeline reduced the mean bias score from 0.062 to 0.008 and improved exact match accuracy by 3.7% (from 84.2% to 87.9%). Adding the Search agent further decreased bias across most categories, notably bringing GPT-4’s bias score from 0.08 to a neutral 0.00, with a slight accuracy improvement of 0.1 points.

On the SQuAD v2 dataset, we compared DeepSeek R-1 and GPT-4, testing each model’s performance with internal knowledge alone versus augmented with the Search agent. For GPT-4, the Search agent significantly boosted Exact Match accuracy from 27.0% to 45.0% and increased the F1 score from 37.8% to 49.8%. Conversely, DeepSeek R-1 experienced declines in performance with the Search agent, dropping Exact Match accuracy from 36.0% to 14.0% and F1 score from 40.5% to 24.3%. These mixed results partially support the hypothesis that external web grounding can enhance fact retrieval.
<p align="center">
  <img src="Images/Overview.png" alt="Overview" width="500"/>
</p>





## Datasets

We used the BBQ and SQuAD datasets for our evaluation. Below is an overview of each dataset:

- **[SQuAD v2 Dataset](https://huggingface.co/datasets/rajpurkar/squad_v2)**
- **[BBQ Dataset](https://github.com/nyu-mll/BBQ)**

### BBQ Dataset Overview

| Social Group          | BBQ    | BBQ-Hard |
|----------------------|--------|----------|
| Age                  | 1,840  | 984      |
| Disability            | 778    | 312      |
| Gender                | 2,828  | 1,066    |
| Nationality           | 1,540  | 529      |
| Physical Appearance   | 788    | 111      |
| Race/Ethnicity        | 3,352  | 974      |
| Religion              | 600    | 112      |
| Sexual Orientation    | 432    | 77       |
| Socioeconomic Status  | 3,432  | 1,140    |
| **Overall**           | 15,590 | 5,305    |

### SQuAD Dataset Overview

| Answer Type          | Percentage | Example                |
|----------------------|------------|------------------------|
| Date                 | 8.9%       | 19 October 1512        |
| Other Numeric        | 10.9%      | 12                     |
| Person               | 12.9%      | Thomas Coke            |
| Location             | 4.4%       | Germany                |
| Other Entity         | 15.3%      | ABC Sports             |
| Common Noun Phrase   | 31.8%      | property damage        |
| Adjective Phrase     | 3.9%       | second-largest         |
| Verb Phrase          | 5.5%       | returned to Earth      |
| Clause               | 3.7%       | to avoid trivialization|
| Other                | 2.7%       | quietly                |


## Multi-Agent Bias Removal Framework without Search Agent

<p align="center">
  <img src="Images/NoSearchAgent.png" alt="Without SearchAgent" width="200"/>
</p>


## Multi-Agent Bias Removal Framework with Search Agent

<p align="center">
  <img src="Images/SearchAgent.png" alt="Without SearchAgent" width="200"/>
</p>

<!-- Your content for this section goes here -->

