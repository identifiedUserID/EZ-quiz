# StudyQuizGen - Your Personalized Study Quiz Generator

[![Project Status](https://img.shields.io/badge/status-idea-blue.svg)](https://www.repostatus.org/#idea)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

## Overview

StudyQuizGen is a desktop application designed to streamline the process of creating and taking quizzes from your lecture notes.  By leveraging the power of Large Language Models (LLMs) and user-friendly GUI libraries, StudyQuizGen helps students efficiently prepare for tests and exams.

**Concept:**

The core idea is to automate the transformation of study notes into interactive quizzes.  Users upload their notes (PDFs, PowerPoints, etc.), and the application uses an LLM API (like Google Gemini or OpenAI's ChatGPT) to generate relevant quiz questions. These questions are then presented in a graphical user interface, allowing for a focused and effective study session.

## Features

*   **Note Upload & Organization:**
    *   Accepts various note formats (PDF, PowerPoint, and potentially more).
    *   Allows users to upload notes directly into the application.
    *   Option to organize notes by week, lecture, or custom categories.
    *   Flexibility for users to manually group and arrange notes.

*   **Automated Quiz Generation:**
    *   Utilizes a chosen Language Model (e.g., Google Gemini, ChatGPT API).
    *   Generates various question types:
        *   Multiple Choice Questions (MCQs)
        *   Fill-in-the-Blank Questions (Future Enhancement)
        *   Matching Questions (Future Enhancement)
    *   Customizable prompts for the LLM to tailor question generation.
    *   Handles large volumes of notes, potentially tens of thousands of slides due to LLM context window capabilities.

*   **Interactive GUI for Quizzes:**
    *   Provides a user-friendly graphical interface for taking quizzes.
    *   Clear presentation of questions and answer options.
    *   Options for:
        *   Immediate feedback after each question.
        *   End-of-quiz summary with score and correct answers.
        *   Detailed feedback and explanations for correct answers and why alternatives are incorrect (powered by LLM).

*   **Customization & Control:**
    *   User selectable Language Model API (with API key input).
    *   Option to choose question types for quiz generation.
    *   Adjustable settings for quiz parameters (number of questions, etc. - Future Enhancement).

## Technical Details & Implementation

*   **Programming Language:** Python (ideal for GUI applications and LLM API interaction)
*   **GUI Library:**
    *   **Tkinter:**  A good starting point for a simple and cross-platform GUI.
    *   **PyQt or PySide6:** More powerful and feature-rich options for a more polished application (consider for future development).
    *   **PyWebUI (or similar):** Explore if a web-based GUI within a desktop application is desired.
*   **Language Model API:**
    *   **Google Gemini API:**  Attractive due to free tier and large context window.
    *   **OpenAI API (ChatGPT):** Another powerful option, user choice for flexibility.
*   **Libraries for Note Processing:**
    *   `PyPDF2` or `pdfminer.six` for PDF text extraction.
    *   `python-pptx` for PowerPoint text extraction.
*   **API Interaction:**  Libraries like `requests` or the specific API client library provided by the LLM provider.

## Potential Workflow

1.  **User Uploads Notes:**  The user drags and drops or selects note files (PDF, PPTX) into the application.
2.  **Note Organization (Optional):** User organizes notes into categories or lectures.
3.  **Quiz Generation Setup:** User selects desired quiz parameters (question types, number of questions - future feature), and chooses the LLM API (and enters API key).
4.  **Quiz Generation (Backend):**
    *   The application extracts text from the notes.
    *   It sends prompts to the chosen LLM API, providing the extracted text and instructions to generate quiz questions (MCQs initially).
    *   The LLM returns questions, answer options, and potentially explanations in a structured format (e.g., JSON).
5.  **GUI Quiz Display:**
    *   The application parses the LLM response and displays the quiz questions in the GUI.
    *   User interacts with the quiz, selecting answers.
6.  **Feedback & Results:**
    *   Based on user settings, feedback is provided after each question or at the end of the quiz.
    *   The application displays the score, correct answers, and LLM-generated explanations.

## Future Enhancements

*   **More Question Types:** Implement Fill-in-the-Blank and Matching question generation.
*   **Quiz Customization:** Allow users to specify the number of questions, topics to focus on, difficulty levels (if LLM allows).
*   **Question Bank Management:** Store generated questions for reuse and editing.
*   **Progress Tracking:** Track user performance over time and across different quizzes.
*   **Offline Mode (Limited):** Explore options for some offline functionality, potentially with smaller, locally run language models for simpler tasks.
*   **Export Quiz Functionality:** Allow users to export quizzes in different formats (e.g., text, CSV, other quiz platforms).
*   **Theming and UI/UX Improvements:** Enhance the visual appearance and user experience of the GUI.

## Getting Started (Development)

1.  **Set up Python Environment:**  Create a virtual environment and install necessary libraries (Tkinter/PyQt, PyPDF2, python-pptx, requests/LLM API client).
2.  **GUI Framework:** Choose and set up your GUI library (Tkinter to start simple).
3.  **Note Parsing:** Implement functions to extract text from PDF and PPTX files.
4.  **LLM API Integration:** Choose an LLM API (Google Gemini is a good starting point), get an API key, and implement basic API calls to generate MCQs from sample text.
5.  **GUI Quiz Display & Interaction:**  Create the GUI elements to display questions and handle user answers.
6.  **Feedback Logic:** Implement logic to check answers and provide feedback.
7.  **Refine and Iterate:**  Test, refine, and add features incrementally.

## License

This project is licensed under the [MIT License](LICENSE). 

---
