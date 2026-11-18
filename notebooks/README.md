# Kaggle scoring notebooks

Each notebook scores one batch of (question, document) pairs with an open-weight reranker on Kaggle (2× T4, fp16). The score files they produced are inputs of the submissions and are shipped in the data package, so the notebooks stay here as provenance. No token or secret is used; all models are public.

| Notebook | Pairs scored | Model |
|---|---|---|
| `s31-kaggle-judge.ipynb` | first reranker pass over the cosine candidate pool | Qwen3 reranker (yes/no judge) |
| `s36-kaggle-4b-final.ipynb` | remaining pairs of the final candidate pools (47,833 pairs) | Qwen3-Reranker-4B |
| `s36-kaggle-4b-final-B.ipynb` | top-20 English PubMed documents per question (24,000 pairs) | Qwen3-Reranker-4B |
| `s37-kaggle-4b.ipynb` | newly collected Chinese documents, batches 1–6 (59,021 pairs) | Qwen3-Reranker-4B |
| `s37-kaggle-4b-b007.ipynb` | newly collected Chinese documents, batch 7 (357 pairs) | Qwen3-Reranker-4B |

The scorer script and model revision are pinned (see [`MODELS.md`](../MODELS.md)). The `sNN` prefix is the development round.
