# Multi-Agent Debiasing Framework with Online Search Based-Validation


<div align="center">
Mughees Ur Rehman (mughees@vt.edu), Ayush Roy (ayushroy24@vt.edu)
</div>


## Abstract

Large language models (LLMs) can produce human-like text, but
they often reflect the biases found in the data used to train them.
There have been various efforts in the past to remove biases from
LLMs. We have proposed a Multi-Agent Bias Removal Framework
(MABRF) designed to systematically detect and mitigate biases
in reasoning while maintaining relevancy in reasoning generated
by LLMs. In our system, Multi-LLM agents work together to de-
tect, evaluate, and mitigate biases in reasoning context. The core
idea is to deploy agents in different settings. We compare two
multi-agent moderation workflows. In the baseline, a Judge agent
evaluates each answer for bias and relevance, and a Rephrasing
agent iteratively refines any biased or off-topic reasoning using
only its internal knowledge. In the enhanced workflow, we add
a search agent that retrieves and summarizes external evidence
before each rephrase, helping the rephrasing agent to obtain exter-
nal knowledge to mitigate bias more efficiently. We evaluated the
approach on the BBQ dataset, conducting experiments with 110
data points across 11 categories (10 per category) using DeepSeek,
GPT-3.5-Turbo, GPT-4, and Claude-3-Haiku. The comparison in-
volved bias scores and accuracy, both with and without the search
agent. On the BBQ benchmark, the baseline MABRF pipeline re-
duced the mean bias score from 0.062 to 0.008, while improving
exact match accuracy by 3.7% (from 84.2% to 87.9%). Incorporating
the search agent further reduced bias across most social categories,
with the most notable result for GPT-4 bias dropped from 0.08
to 0.00 (neutral), and accuracy increased by 0.1 points. For the
SQuAD v2 dataset, we tested DeepSeek R-1 and GPT-4, comparing
each model’s performance with only the LLM’s internal knowledge
against its performance when augmented with the search agent.
For GPT-4, integrating the search agent resulted in significant im-
provements: Exact Match accuracy increased from 27.0% to 45.0%,
and the F1 score rose from 37.8% to 49.8%. In contrast, DeepSeek
R-1 saw a decline, with Exact-Match accuracy dropping from 36.0%
to 14.0%, and the F1 score falling from 40.5% to 24.3%. These mixed
outcomes provide partial support for the hypothesis that external
web grounding enhances fact retrieval.

## Multi-Agent Bias Removal Framework without Search Agent




