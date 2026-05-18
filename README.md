# Synthetic Question Dataset for Off-Topic Detection

Supplementary release accompanying a paper currently under double-blind review.

This repository contains a synthetic dataset of student-style questions across
three university subjects (chemistry, sociology, computer science / algorithms),
together with the generation prompts used to produce them. The dataset is
intended for training and evaluating off-topic / on-topic classifiers for
educational LLM tutors.

## Contents

- `synthetic_questions_chemistry.csv` — questions for the chemistry domain.
- `synthetic_questions_sociology.csv` — questions for the sociology domain.
- `synthetic_questions_computer_science_algorithms.csv` — questions for the
  CS / algorithms domain.
- `synthetic_questions_all_subjects.csv` — concatenation of the three
  per-subject files.
- `synthetic_questions_simple.csv` — a smaller, balanced sample used for the
  main experiments in the paper (500 rows per (subject, category) cell).
- `APPENDIX_PROMPTS.txt` — the prompt templates used to generate each
  category of question.

## Labels

Each row carries a `category` label drawn from:

- `on-topic` — standard in-domain questions.
- `off-topic` — clearly unrelated questions.
- `hard-on-topic` — ambiguous but still in-domain.
- `hard-off-topic` — uses domain vocabulary deceptively (e.g. "chemistry
  between people" for the chemistry domain).

## License

Released for academic use in connection with the paper under review.
