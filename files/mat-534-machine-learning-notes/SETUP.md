# Password-Protected Course Notes Setup

## Overview

Your ML course notes are password-protected using client-side JavaScript. This guide covers setup and customization.

## File Structure

```
files/
└── mat-534-machine-learning-notes/
    ├── protected-notes.html      ← Password gateway (do not rename)
    ├── lecture-01.html           ← Your HTML notes
    ├── lecture-02.html
    └── ...
```

## Quick Setup

### 1. Set Your Password

Edit `files/protected-notes.html` and find this line (around line 187):

```javascript
const PASSWORD_HASH = btoa('changeme');
```

To set a new password:
1. Open browser developer console (F12 or Cmd+Option+I)
2. Run: `btoa('your-password')` (replace with your password)
3. Copy the output and replace in the file

**Example:**
```javascript
// Run in console: btoa('ML2026')
// Output: TUwyMjAyNg==

// Update file to:
const PASSWORD_HASH = 'TUwyMjAyNg==';
```

### 2. Add Your Lecture Notes

In the same file, find the `COURSE_NOTES` section (around line 169):

```javascript
const COURSE_NOTES = {
    'mat-534': {
        title: 'MAT 534: Mathematics for Machine Learning',
        notes: [
            // Add your lectures here
        ]
    }
};
```

Add entries for each lecture:

```javascript
notes: [
    { name: 'Lecture 1: Introduction', file: 'lecture-01.html' },
    { name: 'Lecture 2: Linear Algebra', file: 'lecture-02.html' },
    { name: 'Lecture 3: Calculus', file: 'lecture-03.html' },
]
```

### 3. Place Your HTML Files

Copy all your HTML lecture files into `/files/mat-534-machine-learning-notes/`

Each file should ideally include a back button to return to the notes list. See `lecture-01-example.html` for template.

## Testing Locally

```bash
bundle exec jekyll serve
# Visit http://localhost:4000/files/mat-534-machine-learning-notes/protected-notes.html
```

## Deployment

```bash
git add files/
git add _teaching/
git commit -m "Add ML course notes with password protection"
git push
```

Site automatically builds on GitHub. Access via:
`https://Suraj-Singh-Khurana.github.io/files/mat-534-machine-learning-notes/protected-notes.html`

## How It Works

1. Students visit the gateway page
2. Enter password set in step 1
3. If correct, shows list of all lectures
4. Click to access each lecture HTML file
5. Session stays active until browser closes
6. Click "Logout" to manually clear session

## Teaching Page Integration

The course appears on your teaching page with a direct link. This works because:

**File**: `_teaching/mat-534-mathematics-machine-learning.md`
```yaml
status: "Ongoing"
external_url: "/files/mat-534-machine-learning-notes/protected-notes.html"
```

The teaching archive automatically converts this to a clickable link on `/teaching/` page.

## Security Notes

⚠️ **This solution provides basic privacy protection** by:
- ✅ Preventing casual/accidental access
- ✅ Keeping content away from search engines
- ✅ Session-based (logs out on browser close)

⚠️ **It is NOT suitable for highly sensitive data** because:
- ❌ Password is visible in HTML source
- ❌ Not encrypted, just base64 encoded
- ❌ Anyone with dev tools can bypass

For highly sensitive content, consider:
- Using a Learning Management System (LMS)
- Hosting on a private server with real authentication
- Using GitHub's private pages feature

## FAQ

**Q: Can I use the same gateway for multiple courses?**
A: Yes, duplicate `protected-notes.html` to a new course folder and modify the `COURSE_NOTES` config.

**Q: What if a student forgets the password?**
A: You can change it anytime and redistribute to students. Old sessions will still work until browser closes.

**Q: How do I update lecture notes?**
A: Edit the HTML file directly in `/files/mat-534-machine-learning-notes/` and push to GitHub.

**Q: Can I track who accesses the notes?**
A: Not with this client-side solution. You'd need server-side analytics.

## Support

- Verify file paths match exactly
- Test in browser console before deploying
- Check file permissions are readable
- Ensure `.html` files are well-formed
