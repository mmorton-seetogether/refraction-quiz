# Refraction final assessment – practice quiz

A small, static quiz page for testing the 50 refraction MCQs. Testers choose an answer, select **Submit**, and see whether they were right and which answer is correct. A results screen at the end shows the score by section and lists questions to review. Nothing is saved: refreshing the page starts again.

## Files

| File | What it is |
|---|---|
| `index.html` | The quiz page (layout, styles and logic) |
| `questions.js` | The 50 questions and answer key |
| `tools/docx_to_questions.py` | Rebuilds `questions.js` from the Word document |

## Put it on GitHub Pages

1. Create a new repository on GitHub (it can be public or, with a paid plan, private).
2. Upload `index.html` and `questions.js` (the `tools` folder is optional).
3. In the repository, go to **Settings → Pages**, set **Source** to *Deploy from a branch*, pick `main` and `/ (root)`, then **Save**.
4. After a minute the quiz is live at `https://<your-account>.github.io/<repository-name>/`.

Note: the answer key is in `questions.js`, so anyone who views the page source can see it. That's fine for testing the questions, but not for a real assessment.

## Changing the questions

**Option 1 – edit the Word document, then rebuild:**

```
pip install python-docx
python tools/docx_to_questions.py "Refraction final assessment 50 MCQs.docx"
```

The script expects the same layout as now: *Heading 1* for sections, *Heading 2* for question numbers (Q1, Q2 …), normal paragraphs for the question, *List Paragraph* for options, and `[correct]` at the end of the correct option. It stops with a message if a question has no correct answer marked.

**Option 2 – edit `questions.js` directly.** `answer` is the position of the correct option, counting from 0 (0 = A, 1 = B, 2 = C, 3 = D).

## Try it on your computer

Double-click `index.html`, or run `python -m http.server` in this folder and open http://localhost:8000.
