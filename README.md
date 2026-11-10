# SemEval-2027 Task 2: DiCo-NLI (Group 3)

Course project for **CSCI/LING 5832 Natural Language Processing**, University of Colorado Boulder.

## Team - Group 3

- Hima Varshith Reddy Paduru
- Abhirama Karthikeya Mullapudi

## Task

We are working on [SemEval-2027 Task 2: DiCo-NLI](https://github.com/ilopezgazpio/SemEval-2027-Task-2-DiCo-NLI)
(Directional Consistency in Fine-Grained Natural Language Inference).

**Sub-tasks:** Track 1 (English). Track 4 (Mixed multilingual) is a stretch goal.

Given an ordered pair of short phrases, a system predicts one of four labels:

| Label | Meaning | Example |
| --- | --- | --- |
| `FORWARD_ENTAILMENT` | premise implies hypothesis | "a black dog" → "a dog" |
| `BACKWARD_ENTAILMENT` | hypothesis implies premise | "a dog" → "a black dog" |
| `EQUIVALENCE` | both imply each other | "a large house" → "a big house" |
| `NEGATIVE_OTHER` | any other relation | "a black dog" → "a white cat" |

Every pair also appears in reverse, and systems are scored on **Weighted F1**, **SoftCons**
(are the two directions logically compatible?) and **HardCons** (are both directions correct?).

## Planned approach

Our question: can we make an NLI model directionally consistent without hurting accuracy? We plan to compare:

1. A fine-tuned encoder baseline (DeBERTa-v3)
2. Joint decoding: picking the best logically valid label pair for both directions at inference time
3. A consistency loss that penalizes incompatible predictions during training
4. A zero-shot open-weight LLM

## References

- Task repository: https://github.com/ilopezgazpio/SemEval-2027-Task-2-DiCo-NLI
- Assessing Logical Consistency in Fine-Grained NLI (LREC 2026): https://lrec.elra.info/lrec2026-main-423
