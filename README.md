# Bakery QA Document Control 🍞

> A frontend planning prototype for an internal bakery QA document management website — built in pure HTML, CSS, and JavaScript.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

## About

This prototype was built to plan and demonstrate the UI/UX of a document control system tailored for a bakery's quality assurance workflows. It covers two user roles: **QA Admin** and **Read-Only Staff**.

## Features

### QA Admin Portal
- Document library with custom department folders
- Document preview and fullscreen modal viewing
- Version history per document
- Review reminders and status tracking
- Upload and manage QA documents

### Staff Portal (Read-Only)
- Clean document browser
- Print and download support
- Dark mode toggle
- No editing permissions

## Running Locally

No build step needed — open directly in a browser:

```bash
# Option 1: open directly
open index.html

# Option 2: serve with Python
python3 -m http.server 4173
# then visit http://localhost:4173
```

## Planned Features (Future Backend)

- [ ] Authentication & role-based access control
- [ ] Backend storage and database (document records, users)
- [ ] PDF upload and parsing
- [ ] Document permission levels
- [ ] Audit trail / access log

## License

MIT
