# EzQuiz - AI-Powered Quiz Generator & Solver

[![Project Status](https://img.shields.io/badge/status-idea-blue.svg)](https://www.repostatus.org/#idea)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

## 🚀 Overview

EzQuiz is a standalone, browser-based application designed to generate and solve quizzes interactively. It utilizes Google's Gemini API to analyze uploaded notes (PDF, DOCX, PPT, TXT, PY, etc.) and automatically create well-structured quiz questions. Users can solve the quizzes in an engaging, dynamic interface and receive in-depth performance analytics. 

## 🎯 Features

- 📂 **Upload Notes**: Supports PDF, DOCX, PPT, TXT, PY, and other text-based formats.
- 🔄 **Load Pre-Generated Quiz**: Import quiz JSON files for immediate use.
- 🔗 **Gemini API Integration**: Generates questions and answer feedback dynamically.
- ✅ **Custom Question Types**: Users can select which question types to generate (MCQ, Fill in the Blanks, Matching, Ordering, Short Answer).
- ⏳ **Timer & Analytics**: Tracks time spent per question and provides detailed insights.
- 📊 **Advanced Performance Visualization**:
  - Cumulative time graph (question vs. time)
  - Radar chart (question type performance)
  - Bar graph (subject category performance)
  - Heatmap (difficulty vs. accuracy)
- 🎮 **Kahoot-Style Interactive UI**: Engaging quiz interface with real-time feedback.
- 📥 **Downloadable Results**: Export results as JSON, PDF, or HTML.
- ⚙️ **Customization**: Settings menu to configure themes, quiz behavior, and API key.

---

## 📌 Background & Context

Modern education requires interactive tools that both test knowledge and provide meaningful feedback. Traditional quizzes often lack adaptability, making it difficult for students to assess their weak areas. EzQuiz solves this by:
1. **Automating question creation** – No manual effort required in setting up quizzes.
2. **Standardizing format** – Ensures uniform question output across all attempts.
3. **Providing deep analytics** – Tracks performance trends to help students improve.

---

## 🔥 Example Use Cases

1. **Students**: Quickly generate tests from class notes and assess understanding.
2. **Teachers**: Create quizzes effortlessly for assignments or practice tests.
3. **Corporate Training**: Convert training materials into interactive quizzes.
4. **Interview Preparation**: Practice questions for coding or general knowledge tests.

---

## 🛠️ System Instructions for Gemini API

EzQuiz uses well-defined system prompts to ensure **consistent question format**. Below is a *general, high-level overview* of what the schema looks like.

### **Question Generation Prompt**
```plaintext
You are an AI assistant tasked with generating a quiz in a standardized JSON format based on provided notes. Ensure that:
- Questions are diverse and follow one of the selected types: Multiple Choice (MCQ), Fill in the Blanks, Matching, Ordering, Short Answer.
- The JSON output is **structured consistently**.
- No answer feedback should be generated in this step.

Example JSON Output:
{
  "questions": [
    {
      "question_id": 1,
      "question_type": "MCQ",
      "question_category": "Physics - Newton’s Laws",
      "question": "Which of Newton's Laws explains why a seatbelt protects passengers?",
      "options": ["First Law", "Second Law", "Third Law", "None of the above"],
      "correct_answer": "First Law"
    }
  ]
}
```

### Answer Feedback Prompt

```
Now, generate **detailed feedback** for the previously generated questions. Ensure:
- Every MCQ option has feedback explaining why it is right or wrong.
- Fill in the Blanks provide an explanation for the correct answer.
- Matching questions include justifications for all correct pairs.
- Ordering questions include the correct order and reasoning.
- Short Answer questions provide a model response.

Example JSON Output:
{
  "answers": [
    {
      "question_id": 1,
      "feedback": {
        "First Law": "✅ Correct! Newton’s First Law states that an object in motion remains in motion unless acted upon by an external force. The seatbelt provides this force.",
        "Second Law": "❌ Incorrect. The Second Law deals with force and acceleration, not inertia.",
        "Third Law": "❌ Incorrect. This law describes action-reaction forces, which do not explain seatbelt mechanics.",
        "None of the above": "❌ Incorrect. Newton's Laws specifically explain this phenomenon."
      }
    }
  ]
}
```

## 📜 JSON Schema Definitions

### Quiz Question JSON Schema

```
{
  "questions": [
    {
      "question_id": "integer",
      "question_type": "string",
      "question_category": "string",
      "question": "string",
      "options": ["string", "string", "string", "string"],
      "correct_answer": "string"
    }
  ]
}
```

### Quiz Answer Feedback JSON Schema

```
{
  "answers": [
    {
      "question_id": "integer",
      "feedback": {
        "option_1": "string",
        "option_2": "string",
        "option_3": "string",
        "option_4": "string"
      }
    }
  ]
}
```

## 🎨 UI & Design Principles

- Selection Menu: Users choose between file upload or loading a pre-generated quiz JSON.
- Dynamic Loading Screen: Animated progress indicators while processing.
- Kahoot-Style Interface:
  - Large, color-coded answer buttons for MCQs.
  - Interactive matching and ordering question styles.
- Analytics Dashboard:
  - 📈 Line Graph: Time spent per question.
  - 🕵️ Radar Chart: Performance across question types.
  - 📊 Bar Graph: Accuracy per subject category.
  - 🔥 Heatmap: Time vs. accuracy correlation.
Exportable Reports: Downloadable quiz results as JSON, PDF, or HTML.

## 📝 Product Backlog Overview

### Core Features
- ✅ File Upload (PDF, DOCX, etc.)
- ✅ Pre-Generated Quiz Loader (JSON)
- ✅ Gemini API Integration for Question Generation
- ✅ Question Type Selection
- ✅ Dynamic Loading Animation

### Quiz & UI Enhancements
- ✅ Kahoot-Style UI for MCQs
- ✅ Real-Time Timer & Analytics
- ✅ Flagging & Reviewing Questions
- ✅ Customizable Themes (Light/Dark Mode)

### Advanced Analytics
- ✅ Cumulative Time Graph (Question vs. Time)
- ✅ Radar Chart (Accuracy by Question Type)
- ✅ Heatmap (Difficulty vs. Accuracy)
- ✅ Multi-Attempt Progress Comparison

### Export & Reports
- ✅ JSON, PDF, and HTML Quiz & Result Export
- ✅ Study Recommendations Based on Weak Areas

### 🤝 Contributions & Feedback

We welcome contributions! Please fork the repo, make your changes, and submit a pull request. Found a bug or have a suggestion? Open an issue! 🚀

## License

This project is licensed under the [MIT License](LICENSE). 

---
