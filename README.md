# For ESG
## Tasks
- summarization - improve prompt
- japanese LLM performance
- pdf loader
    - meaningful groups of texts
    - newlines
    - layouts
    - https://python.langchain.com/docs/modules/data_connection/document_loaders/pdf

## Why
- レポートからESGに関する情報を抜き出すの大変
    - フォーマットに沿ってない
    - でも聞くことは大体決まってる
        - ふわっと抜き出す（要約など）
        - 確実に抜き出す（数値など）
- 同一会社のESGを過去に遡って比較したい
- TCFDレポートであっても、抜き出すのをなんとかしたい

## What
- look at a glance then deep dive into section
- extract exact number/info
    - e.g. 女性管理職の割合
- extract fuzzy answer per prepared question
    - e.g. 目標とか？
- extract then generate in a certain format?
- batch job on multiple reports

## How
1. summarization (map-reduce)
    1. entire content (落合フォーマット?)
    1. per section or paragraph (based on splitter)
1. info extraction / rag
    1. tech: vectorstore? knowledge graph?
    1. extract a certain number
    1. extract and generate?
1. document transformation?
    1. how?
1. (performing LLM on all docs w/o VS/KG)

# Others
- co-oncall - Xianfeng
    - VS/KG…
    - query expansion
    - rewrite RAG
- policy reviewer - Romanos
    - MRM
---
data load -> vectorstore/KG -> LLM
-> 

- RAG
    - splitter - how?
    - ragas, arize, guardrails
 
- summarization using stuff, map, and refine - Romanos, Mayu
    - give users the capability to control splitting
- information extraction
    - use the existing research
- transform doc to doc1 - Romanos, Mayu
    - MRM, TCFD, etc
    - how to make prompt? evaluate?
