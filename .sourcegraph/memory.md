# Project Memory

## Commands
- No formal build/test commands in this project
- Changes are published with: `git commit` followed by `git push`

## Project Purpose
This repo scrapes solved questions from Sourcegraph's community forum and creates a structured JSON file containing the questions and answers. The process uses TP to extract content and Gemini to improve the writing.

## Code Conventions
- JSON format: Use proper JSON array format with objects
- Each answer follows schema: `{"url": "", "title": "", "answer": ""}`
- JSON indentation: 2 spaces
- Answer text: Professionally written, clear explanations
- Keep original URL exactly as provided
- When adding new answers, append to the array in answers.json
- Ensure JSON remains valid after modifications