# Synthetic Question Dataset and Prompts for Off-Topic Detection

Supplementary release accompanying a paper currently under double-blind review.

This repository contains (a) a synthetic dataset of student-style questions
across three university subjects (chemistry, sociology, computer science /
algorithms), and (b) the full prompt set used in the paper, including the
**decoupled classifier prompt** introduced in the revision.

## For reviewers — start here

If you are looking for the decoupled-classifier prompt referenced in the
revision (system message, user-message template, the 12 few-shot exemplars
across the three subjects, the RAG variant, and the API parameters), it is
in `APPENDIX_PROMPTS.txt`, **Section 8 (Decoupled Classifier Prompt)** and
**Section 9 (API Parameters)**. These are the items most relevant to
evaluating the new T1 / T2 experiments.

The rest of `APPENDIX_PROMPTS.txt` (Sections 1–7) reproduces the prompt
set from the original submission — data generation, tutor system prompts
at the three strictness levels, the PARDEN follow-up, ground-truth
labelling prompts, and the detection markers.

## Contents

- `APPENDIX_PROMPTS.txt` — all prompts used in the paper.
  - Sections 1–7: original-submission prompts (data generation, tutor
    system prompts, PARDEN, ground-truth labelling, markers, subjects,
    models).
  - **Section 8: decoupled classifier prompt (NEW — added in revision).**
    System message, user-message template, RAG-augmented variant, and
    all twelve few-shot exemplars (4 per subject × 3 subjects).
  - **Section 9: API parameters** (model, temperature, max_tokens,
    response_format, sampling seed, n per cell, RAG configuration).
- `synthetic_questions_simple.csv` — the evaluation question pool. Four
  columns: `subject, category, question, label`. 500 items per
  (subject, category) cell — 3 subjects × 4 categories × 500 = 6 000 rows.
  This is the file sampled from in the paper's experiments (n=100 per
  cell, seed=42).
- `synthetic_questions_chemistry.csv`,
  `synthetic_questions_sociology.csv`,
  `synthetic_questions_computer_science_algorithms.csv` — per-subject
  experimental run logs from the original submission (one row per
  (question × prompt-strictness × model) cell, with the tutor response,
  PARDEN follow-up, and detection flags).
- `synthetic_questions_all_subjects.csv` — concatenation of the three
  per-subject run-log files.

## Category definitions

- `on-topic` — standard in-domain questions a first-year student would
  ask.
- `hard-on-topic` — ambiguous, advanced, or awkwardly phrased, but the
  intent is still to learn the subject.
- `off-topic` — clearly unrelated to the subject.
- `hard-off-topic` — uses domain vocabulary or concepts but the intent
  is not about the subject (e.g. the catalysis-of-influencers example
  in Section 8.4 of the appendix).

## License

Released for academic use in connection with the paper under review.
