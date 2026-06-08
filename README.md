# Distorted Visual Sequence Pattern Recognition

OCR system for heavily occluded grayscale text sequences. Evolved through four architectures (CNN, CRNN+STN, 1D Transformer, 2D Spatial Transformer), with the final Transformer achieving **99.5% character accuracy** and **97.55% exact sequence match** on the validation set.

---

## Repository Contents

| File | Description |
|------|-------------|
| `distorted_ocr_submission.ipynb` | Full pipeline: EDA, all four approaches, training loops, and final inference |
| `best_seq2seq_ocr.pth` | Final model checkpoint (1D Transformer Seq2Seq, best val CER = 0.0050) |
| `submission_rishav_24323032.csv` | Final test set predictions |
| `Distorted_OCR_Project_Report.pdf` | Project report |
| `Problem_Statement.pdf` | Original problem statement |

---

## Reproducing the Submission

Place `best_seq2seq_ocr.pth` and `test_images/` in the same directory, then run the last cell of the notebook. The output is `submission_rishav_24323032.csv`.

---

## Results Summary

| Approach | Architecture | Val CER |
|----------|-------------|---------|
| 1 | Naive CNN + CTC | 0.9351 |
| 2 | CRNN + STN + CTC | ~0.90 (stalled) |
| 3 | 1D Transformer Seq2Seq | **0.0050** |
| 4 | 2D Spatial Transformer | 0.0232 (ep 12) |

**Submitted model:** Approach 3 (trained to 40 epochs). Approach 4 benchmarked at 12 epochs shows faster convergence and 21.6% higher throughput at identical parameter count (3.35M).


Made by Rishav Kumar
