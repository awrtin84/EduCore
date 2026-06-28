# 🤝 Contributing to EduCore

Welcome to **EduCore**!

EduCore is a modern University Management System built with **FastAPI** and **Next.js**.

Our goal is not just to build software, but to build it using professional software engineering practices.

Please read this guide before contributing.

---

# 🎯 Project Goal

EduCore aims to become a complete University Management System (UMS).

The project is designed to be:

- Modular
- Scalable
- Maintainable
- Production Ready

---

# 👥 Team Roles

## Project Owner

Responsible for:

- Project management
- Final technical decisions
- Pull Request approvals
- Sprint planning

---

## Developers

Responsible for:

- Developing new features
- Fixing bugs
- Writing clean code
- Updating documentation

---

## Technical Lead

Responsible for:

- Software Architecture
- Database Design
- API Design
- Code Review
- Best Practices
- Development Planning

---

# 🌳 Git Workflow

## Main Branches

### main

Production-ready code only.

No direct commits are allowed.

---

### develop

Main development branch.

All completed features are merged into this branch.

No direct commits are allowed.

---

## Feature Branches

Every new feature must have its own branch.

Examples:

```
feature/authentication
feature/backend-refactor
feature/student-module
feature/course-module
feature/dashboard
```

Feature branches must be created from **develop**.

---

# 🚫 Branch Rules

❌ Never commit directly to **main**

❌ Never push directly to **develop**

✅ Always use Pull Requests

---

# 📌 Issues

Every task must start with an Issue.

This includes:

- New Features
- Bug Fixes
- Improvements
- Documentation

Examples:

```
Implement JWT Authentication

Refactor Course Module

Add Student CRUD

Fix Duplicate Registration Bug
```

---

# 📋 Project Workflow

Every task follows this lifecycle:

```
Backlog
   ↓
Todo
   ↓
In Progress
   ↓
Review
   ↓
Testing
   ↓
Done
```

## Status Description

### Backlog

Ideas that are not scheduled yet.

---

### Todo

Ready to start.

---

### In Progress

Currently being developed.

---

### Review

Waiting for code review.

---

### Testing

Merged into develop and under testing.

---

### Done

Completed successfully.

---

# 🔀 Pull Request Rules

Before opening a Pull Request:

- Project must build successfully
- No errors
- Clean commit history

Every Pull Request must include:

- Clear title
- Description
- Related Issue

Example:

```
Closes #12
```

After approval:

- Merge into develop
- Delete feature branch

---

# 💬 Commit Message Convention

We use **Conventional Commits**.

Examples:

```
feat(auth): add JWT authentication

feat(student): implement CRUD endpoints

fix(course): resolve duplicate registration bug

refactor(database): simplify repository layer

docs: update project roadmap

test(auth): add login tests

chore: update dependencies
```

---

# 📂 Project Structure

```
backend/
frontend/
database/
docker/
docs/
```

Do not place unnecessary files in the project root.

---

# 🧹 Coding Standards

Every code contribution should be:

- Readable
- Clean
- Modular
- Reusable
- Maintainable

Avoid:

- Duplicated code
- Magic numbers
- Long functions
- Poor naming

Use meaningful names for:

- Variables
- Functions
- Classes
- Files

---

# 🏗 Backend Rules

Business logic must NOT be inside Routers.

Use the following architecture:

```
Router
    ↓
Service
    ↓
Repository
    ↓
Database
```

Validation belongs to Schemas.

Database operations belong to Repositories.

Business logic belongs to Services.

---

# 🎨 Frontend Rules

Components should be:

- Small
- Reusable
- Maintainable

API requests should be handled through Services.

Avoid unnecessary Client Components.

---

# 🧪 Testing

Every important feature should be tested.

Every bug fix should include a test whenever possible.

---

# 📚 Documentation

Every important feature must be documented.

Every architectural decision should be recorded.

Every API should eventually be documented.

---

# ⭐ Development Philosophy

We value:

- Quality over speed
- Clean architecture
- Team collaboration
- Continuous learning
- Documentation
- Best practices

---

# ❤️ Team Culture

- Respect everyone.
- Ask questions.
- Help each other.
- Learn together.
- Share knowledge.
- Write code that others can understand.

---

# 🚀 EduCore Development Flow

Every feature follows this process:

```
Issue
   ↓
Project Board
   ↓
Feature Branch
   ↓
Development
   ↓
Commit
   ↓
Pull Request
   ↓
Code Review
   ↓
Merge
   ↓
Delete Branch
```

---

# 💙 EduCore Philosophy

> We are not just writing code.

> We are building a real software product.

Let's build something we're proud of.