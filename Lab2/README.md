# ARTI308 – Lab 2: Exam Score Prediction (Regression)

## Overview
This lab applies machine learning to predict a student’s **exam score** using academic and lifestyle features. The workflow includes loading the dataset, inspecting its structure, preprocessing the data, training a regression model, and evaluating performance.

## Dataset
The dataset contains student-related attributes such as:
- `student_age`, `gender`, `course`
- `study_h` (study hours), `class_att` (class attendance)
- `internet` access
- `sleep_h` (sleep hours), `sleep_q` (sleep quality)
- `study_m` (study method), `facility_r` (facility rating)
- `exam_d` (exam difficulty)

## Target Variable (y)
- **`exam_score`** → numeric score (e.g., 0–100)

## Features (X)
- All remaining columns are used as input features.

## Problem Type
✅ **Regression**  
Because the target variable (`exam_score`) is a continuous numeric value.
