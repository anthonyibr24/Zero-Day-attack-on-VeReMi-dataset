Evaluating Zero-Day Attack Generalisation in Machine Learning-Based VANET Intrusion Detection

This repository contains the implementation and experiments for the paper:

“Evaluating Zero-Day Attack Generalisation in Machine Learning-Based VANET Intrusion Detection”

The project investigates the ability of different machine learning (ML) models to detect unseen vehicular cyberattacks using a Leave-One-Attack-Out (LOAO) evaluation strategy on the VeReMi NextGen dataset.

Overview

Traditional Intrusion Detection Systems (IDS) in Vehicular Ad Hoc Networks (VANETs) are commonly evaluated using benchmark train-test splits where attack patterns are already present during training. While these approaches often achieve high accuracy, they may fail to generalise to zero-day attacks — attacks that were never seen during training.

This project evaluates how well ML models generalise to unseen vehicular attacks by:

Training on known attacks
Testing on a completely unseen attack type
Comparing benchmark and zero-day performance
Features
Benchmark ML evaluation on VeReMi NextGen
Leave-One-Attack-Out (LOAO) zero-day evaluation
Engineered sender–receiver relational features
Comparison of multiple ML algorithms
Evaluation using:
Accuracy
Precision
Recall
F1-score
ROC-AUC
Zero-day attack heatmaps and performance visualization
Machine Learning Models

The following models are implemented and evaluated:

Random Forest (RF)
XGBoost
Naive Bayes
Logistic Regression (LR)
Extra Trees (ET)
Dataset

This work uses the VeReMi NextGen dataset.

Dataset Characteristics
1.7M+ samples
25 engineered features
Multiple VANET attack scenarios
Binary classification:
0 = benign
1 = attack
Selected Zero-Day Attacks

The following attacks were used for LOAO evaluation:

dataReplay
dosAttack
reversedHeading
suddenStop
trafficCongestionSybil
Engineered Features

Additional features were generated to improve anomaly detection and zero-day generalisation, including:

Absolute positional noise
Speed noise
Acceleration noise
Sender–receiver speed difference
Sender–receiver acceleration difference
Euclidean positional distance

These features help capture abnormal vehicular communication behaviour.

Methodology
Benchmark Evaluation

Models are trained and tested using known attack distributions.

Zero-Day Evaluation (LOAO)

For each experiment:

One attack type is removed from training
The model is trained on all remaining attacks
The unseen attack is used only during testing

This simulates realistic zero-day attack scenarios.

Results Summary
Benchmark Results

Tree-based ensemble models achieved the strongest benchmark performance:

XGBoost achieved the highest overall F1-score
Extra Trees showed balanced precision and recall
Random Forest achieved strong recall but higher false positives
Zero-Day Results
Significant performance degradation occurred across all models
XGBoost and Extra Trees demonstrated stronger generalisation capability
Naive Bayes and Logistic Regression performed poorly on unseen attacks
Several attacks produced high recall but very low precision, indicating excessive false positives

The results demonstrate that:

High benchmark accuracy does not guarantee reliable zero-day attack detection performance.
