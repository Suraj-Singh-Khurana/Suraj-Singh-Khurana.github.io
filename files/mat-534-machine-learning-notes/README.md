# Setting Up Password-Protected Course Notes

## Quick Start

### 1. **Upload Your HTML Files**
Place all your HTML course notes in this directory:
```
files/mat-534-machine-learning-notes/
├── lecture-01.html
├── lecture-02.html
├── lecture-03.html
└── ...
```

### 2. **Configure the Password**

Edit `/files/protected-notes.html` and find this line (around line 187):

```javascript
const PASSWORD_HASH = btoa('changeme'); // Default: "changeme"
```

**To set a new password:**

1. Open your browser's developer console (F12 or Cmd+Option+I)
2. Run this command with your desired password:
   ```javascript
   btoa('your-new-password-here')
   ```
3. Copy the output and replace `changeme` in the code
4. Example: If your password is `ML2026`, run `btoa('ML2026')` and you'll get `TUwyMjAyNg==`
5. Update the line to:
   ```javascript
   const PASSWORD_HASH = 'TUwyMjAyNg==';
   ```

### 3. **Add Your Course Notes to the List**

In the same file, find the `COURSE_NOTES` section (around line 167):

```javascript
const COURSE_NOTES = {
    'mat-534': {
        title: 'MAT 534: Mathematics for Machine Learning',
        notes: [
            { name: 'Lecture 1: Linear Algebra', file: 'lecture-01.html' },
            { name: 'Lecture 2: Calculus for ML', file: 'lecture-02.html' },
            { name: 'Lecture 3: Probability', file: 'lecture-03.html' },
        ]
    }
};
```

Add an entry for each lecture/note file you have.

### 4. **Link from Your Teaching Page**

Update `_teaching/mat-534-mathematics-machine-learning.md`:

```markdown
---
title: "MAT 534 Mathematics for Machine Learning"
collection: teaching
type: "Course"
permalink: /teaching/mat-534-mathematics-machine-learning
venue: "SRM University AP"
date: 2026-01-01
location: "Andhra Pradesh, India"
status: "Ongoing"
external_url: "/files/protected-notes.html"
---

This is a course on mathematics fundamentals for machine learning applications.

Students can access course notes [here](/files/protected-notes.html) with credentials provided in class.
```

### 5. **Access Your Notes**

- Share the link: `https://your-domain.com/files/protected-notes.html`
- Students enter the password to access all course materials
- Session is maintained during browser session (logs out when browser closes)

---

## Security Notes

⚠️ **Important:** This method provides:
- ✅ **Basic privacy protection** against casual access
- ✅ **Works on GitHub Pages** (no server required)
- ✅ **Session-based** (logs out when browser closes)

⚠️ **Limitations:**
- ❌ Not suitable for highly sensitive data
- ❌ Password is visible in page source (client-side verification)
- ❌ For production/sensitive content, use server-side authentication

For a more secure solution, consider:
- Using GitHub's private pages feature
- Setting up authentication via Netlify or Vercel
- Using a dedicated LMS platform

---

## File Structure

```
files/
├── protected-notes.html          ← Main access page (edit password & note list here)
└── mat-534-machine-learning-notes/
    ├── lecture-01.html
    ├── lecture-02.html
    └── lecture-03-example.html   ← Template example
```

---

## Tips

1. **Test your password** before sharing with students
2. **Use memorable but non-obvious passwords** (avoid common patterns)
3. **Distribute password securely** (during first class, email, etc.)
4. **Keep notes organized** with clear naming conventions
5. **Include back links** in your HTML files to return to the main notes page

---

## Questions?

Refer to:
- [Static site generation with Jekyll](https://jekyllrb.com/)
- [GitHub Pages documentation](https://docs.github.com/en/pages)
