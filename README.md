# Submission 5 - Deep Learning-Based Malware Classification Using Convolutional Neural Networks on Opcode Sequences (Project 1)

This repository contains the deliverables for Submission 5, including 
CNN implementation, evaluation, and comparative analysis against the 
classical machine learning baselines from Submission 4.

## Overview

This project implements the deep learning method proposed by McLaughlin 
et al. in "Deep Android Malware Detection" (CODASPY 2017), adapted for 
multi-class classification of Windows PE malware families using x86 
opcode sequences. Results are compared directly against the SVM, KNN, 
and Decision Tree classifiers from Submission 4.

## Payload Archive

Due to GitHub file size limitations, the scripts, dataset, and output 
archive is provided as a GitHub Release asset. Please download the ZIP 
file from the **Releases** section of this repository:

https://github.com/ArshdeepMCIT/Submission_5/releases/tag/submission_5

## Requirements

- Python 3.11 or later
- Libraries: torch, numpy, pandas, scikit-learn, matplotlib

To install all dependencies:
```
pip install -r requirements.txt
```

## The submitted .zip file contains:

- Dataset/ → raw opcodes, chunked opcodes, processed encoded arrays
- Scripts/preprocessing/ → preprocessing pipeline scripts
- Scripts/ → CNN training, evaluation, and GroupKFold scripts
- Output/ → confusion matrices, metrics, training history, saved model
- requirements.txt → required libraries with versions
- Submission5_FinalReport.pdf → technical report

## Steps to Run

1. Run preprocess_opcodes.py to clean and normalize raw opcode files
2. Run chunk_opcodes.py to generate fixed-length opcode segments
3. Run make_chunked_labels.py to assign malware family labels
4. Run prepare_sequences.py to build vocabulary and encode sequences
5. Run train_cnn.py to train the CNN model
6. Run evaluate_cnn.py to generate final metrics and confusion matrix
7. Run train_cnn_groupkfold.py for leakage-free GroupKFold evaluation

## Models Used

- Convolutional Neural Network (CNN) - Submission 5
- SVM, KNN, Decision Tree - Submission 4 baselines

## Evaluation Metrics

- Accuracy
- Precision (Macro)
- Recall (Macro)
- F1 Score (Macro)
- Confusion Matrix

## Evaluation Strategy

- Standard: Stratified train/validation/test split with random seed 42
- Leakage-Free: GroupKFold (5 folds) by source file

## Notes

This project was completed as part of MCIT coursework.
All results were validated and analyzed carefully.
Full implementation details are provided in the technical report.

## AI Usage Disclosure
This project was developed with assistance from AI tools including 
Claude (Anthropic) and ChatGPT (OpenAI) for code support and grammar 
refinement. All outputs were reviewed and validated by the authors.
