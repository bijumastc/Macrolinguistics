# Macrolinguistics
Introduction to Sociolinguistics, Psycholinguistics, computational linguistics, etc.
# 🌍 Macro Twin

**Your Digital Learning Companion for Introduction to Macrolinguistics**

Macro Twin is a single-page web application designed for undergraduate linguistics students taking an Introduction to Macrolinguistics course. It combines interactive study material, two graded test sets, and a results dashboard — all in one self-contained HTML file with no build step or framework dependencies.

---

## Features

### 📚 Learn Macrolinguistics
An expandable topic-wise study guide covering 13 branches of macrolinguistics:

1. Sociolinguistics — Language and Society
2. Anthropological Linguistics — Language and Culture
3. Graphemics — The Study of Writing Systems
4. Neurolinguistics — Language and the Brain
5. Psycholinguistics — Language and the Mind
6. Cognitive Linguistics — Language and Thought
7. Biolinguistics — The Biology of Language
8. Developmental Linguistics — Child Language Acquisition
9. Historical Linguistics — Language Change Over Time
10. Stylistics — The Linguistic Study of Style
11. Ethnolinguistics — Language and Ethnic Worldview
12. Philosophy of Language — The Nature of Meaning
13. Computational Linguistics — Language and Computers

Each topic includes key ideas, real-world examples, famous linguists, important books, and a summary chart comparing all branches at a glance.

### 📝 Set 1 — Multiple Choice Questions (25 marks)
25 MCQs covering all 13 branches of macrolinguistics (1 mark each). Questions are generalised — focused on understanding what each branch studies, its scope and core concepts (e.g., "What does sociolinguistics study?", "Neurolinguistics studies the relationship between…"). Select an answer to get instant feedback with correct/incorrect indicators, the right answer highlighted, and a clear explanation.

### ✍️ Set 2 — Short & Long Answer (50 marks)
- **Section A:** 10 short-answer questions × 2 marks each (20 marks)
- **Section B:** 6 long-answer questions × 5 marks each (30 marks)

Questions are generalised and branch-focused (e.g., "What is psycholinguistics?", "What is historical linguistics?") rather than testing specific linguist names or theories. Students write their answer, submit it, then see the model answer. They self-rate honestly using a four-level scale (Missed most points / Got some ideas right / Mostly correct / Nailed it). Each question includes a hint to nudge thinking.

### 📊 Results & Twin Encouragement
After completing a test, students see:
- Score ring with percentage and grade
- Topic-wise strength bars showing strong, medium and weak areas
- Personalised encouragement from the "Macro Twin" based on performance level
- Specific next steps recommending which topics to review

The Twin adapts its tone to the student's score — celebrating strong results, encouraging average ones, and offering warm support for weaker performances.

### 📊 Teacher Dashboard
- Password-protected login (credentials: `admin` / `macro2024`)
- View all student submissions with summary statistics
- Data table with Roll No, Name, Set, Score, Grade, Status and Date

### Additional Features
- 🌙 **Automatic dark mode** via `prefers-color-scheme`
- 📱 **Mobile-responsive** layout — works on phones, tablets and desktops
- 💾 **Local storage** backup of all results (`macTwinResults` key)
- ⏸️ **Incomplete test saving** — exiting mid-test saves partial progress
- 🔄 **Retake support** — students can retake tests and track improvement

---

## Project Structure

```
macrolinguistics-twin/
├── index.html    # Complete app (HTML + CSS + JS, single file)
└── README.md     # This file
```

The entire application lives in `index.html` — no external CSS or JS files, no npm dependencies, no build step. Just open the file in a browser.

---

## Setup

### Deploy on GitHub Pages

1. Create a new GitHub repository
2. Upload `index.html` to the repository
3. Go to **Settings → Pages**
4. Under "Source", select **main** branch and **/ (root)**
5. Click **Save**
6. Your app will be live at `https://<username>.github.io/<repo-name>/`

### Run Locally

Simply double-click `index.html` to open it in any modern browser. No server required.

---

## Teacher Dashboard

Access the dashboard from the home screen by tapping **📊 Teacher Dashboard**.

- **Username:** `admin`
- **Password:** `macro2024`

The dashboard reads from `localStorage`, displaying all student submissions made on that device/browser. To change the password, search for `macro2024` in `index.html` and replace it.

---

## Technical Details

| Aspect | Detail |
|--------|--------|
| **Architecture** | Single-page application (SPA) with screen-based navigation |
| **Rendering** | Vanilla HTML/CSS/JS — no frameworks |
| **Theme** | CSS custom properties on `:root` with `@media(prefers-color-scheme:dark)` |
| **Local storage** | `localStorage` key `macTwinResults` stores JSON array of past results |
| **Browser support** | Any modern browser (Chrome, Firefox, Safari, Edge) |
| **File size** | Single HTML file, under 100 KB |

---

## Customisation

### Adding/Editing Questions

Questions are defined as JavaScript arrays in the `<script>` block:

- `mcqData` — Set 1 MCQs (25 items)
- `saData` — Set 2 Short & Long Answer (16 items: 10 × 2 marks + 6 × 5 marks)

**MCQ format:**
```javascript
{ topic:'sociolinguistics', q:'What does sociolinguistics primarily study?',
  options:['The biological basis of language','The relationship between language and society',
           'The history of language change','How computers process language'], correct:1,
  explain:'Sociolinguistics studies the relationship between language and society.' }
```

**Short/Long answer format:**
```javascript
{ topic:'neurolinguistics', marks:2,
  q:'What is neurolinguistics? What are its main concerns?',
  hint:'Think about the connection between language and the brain.',
  model:'Neurolinguistics is the study of how language is represented and processed in the human brain...' }
```

### Adding Learn Topics

1. Add a key to the `TOPICS` object: `computational: { name:'Computational Linguistics', icon:'💻' }`
2. Add an entry to the `LEARN_DATA` array with `topic`, `title` and `content` (HTML string)
3. Update the summary chart in the `overview` entry

### Changing the Theme

Edit the CSS custom properties in the `:root` and `@media(prefers-color-scheme:dark)` blocks. Key variables: `--accent`, `--bg`, `--card`, `--text`, `--good`, `--avg`, `--weak`.

### Changing the Dashboard Password

Search for `macro2024` in `index.html` and replace with your preferred password.

---

## License

This project was created for educational use in an Introduction to Macrolinguistics university course.

---

## Credits

Built with ❤️ for linguistics students.
