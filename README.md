# Mental Health Text Classification with OpenAI (In-Context Learning)

This project demonstrates how to use OpenAI's Chat API for classifying short text statements into mental health categories using in-context learning and chain-of-thought (CoT) prompting.

The classification model identifies one or more of the following mental health categories:
- Normal
- Depression
- Suicidal
- Anxiety
- Stress
- Bipolar
- Personality disorder

No fine-tuning or model training is needed. Everything is powered through prompt design and few-shot examples.

## Overview

- Uses OpenAI's `chat.completions` endpoint for zero-shot, single-shot, and few-shot classification.
- Prompts are modular and customizable: users can easily swap in their own `base_messages` format.
- Supports Chain-of-Thought reasoning and contrastive examples to help the model distinguish between overlapping categories.
- Evaluation is done using accuracy, macro F1, and weighted F1 scores across multiple prompt strategies.
- Ideal for rapid experimentation with in-context classification tasks using language models.

## How to Use

1. Clone this repo and open it in Google Colab or your preferred Python environment.
2. Set your OpenAI API key.
3. Load or customize one of the provided prompt templates (e.g., single-shot, few-shot with CoT, contrastive).
4. Run batch evaluation or single-example generation using:
   - `run_batch_messages_with_prompts(...)`
   - `evaluate_model(...)`

You can also plug in your own `base_messages` format by following the same message structure used in OpenAI's Chat API:
```python
[
    {"role": "system", "content": "..."},
    {"role": "user", "content": "..."},
    {"role": "assistant", "content": "..."},
    ...
]
```

## References

- Sentiment Analysis for Mental Health Dataset (Kaggle):  
  https://www.kaggle.com/datasets/suchintikasarkar/sentiment-analysis-for-mental-health/data  
  Used as the source of short mental health-related text samples for classification tasks.

