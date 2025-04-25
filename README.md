# Chat2SQL: Generating SQL Queries from Natural Language

A Natural Language to SQL translation system using fine-tuned transformer models. This project was developed as part of an academic course and explores the use of models like PLBART, BART, and BERT to automatically generate SQL queries from plain English, trained on datasets like WikiSQL and bmc2/sql-create-context.

## 🚀 Project Overview

The goal of this project is to make querying databases more accessible by enabling users to input natural language queries and receive executable SQL in return. We fine-tuned transformer-based models for this task and benchmarked them on two widely used datasets.

## 📚 Datasets

- **WikiSQL**: Over 80,000 natural language question/SQL pairs with simple schemas (single-table).
- **bmc2/sql-create-context**: Roughly 78,000 pairs with more complex schemas including multi-table/nested queries.

## 🧠 Models Used

- **PLBART** – Pretrained on both code and natural language.
- **BART** – Encoder-decoder transformer architecture.
- **BERT** – Encoder-only, adapted for sequence generation.
- **LLaMA-3B** – Used in zero-shot mode for comparative baseline.

## 🧪 Evaluation Metrics

- **BLEU Score** – Token-level overlap between generated and ground-truth SQL.
- **Execution Accuracy** – Whether the generated query executes and returns the correct result.

### Results Summary

| Model       | Dataset               | BLEU Score |
|-------------|------------------------|------------|
| PLBART      | bmc2                   | 0.820      |
| PLBART      | WikiSQL                | 0.768      |
| BART        | bmc2                   | 0.714      |
| BART        | WikiSQL                | 0.755      |
| BERT        | bmc2                   | 0.645      |
| BERT        | WikiSQL                | 0.620      |
| LLaMA-3B    | WikiSQL (zero-shot)    | ~0.70      |

## 🛠 How to Run

1. Clone the repository.
2. Open the appropriate notebook for the dataset and model of interest:
   - `BART_bmc2.ipynb`
   - `Bart_WikiSQL.ipynb`
   - `bert_wikisql.ipynb`
   - `Bert bmc2.ipynb`
   - `WikiSQL_PLBart_New.ipynb`
3. Install dependencies using:
   ```bash
   pip install -r requirements.txt
