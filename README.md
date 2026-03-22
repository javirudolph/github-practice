# github-practice

**This is the README in Colleen's branch.**

A hands-on repository to learn GitHub's essential features: commits, branches, pull requests, and issues.

**Associated blog post:** [Why I love Git and Github](https://javirudolph.github.io/posts/2025-02-20-git-and-github/)

---

## Why Use Git and GitHub?

Git helps you:
- **Track changes** without saving multiple file versions (`script_v1.R`, `script_v2_FINAL.R`, `script_v2_FINAL_ACTUALLY.R`)
- **Experiment safely** by creating test branches
- **Collaborate effectively** with clear history of who changed what and when
- **Recover from mistakes** by reverting to previous versions

GitHub adds:
- Cloud backup of your work
- Easy collaboration and code sharing
- Professional portfolio of your projects

---

## Getting Started

### Prerequisites

**Before you begin, you need:**

1. **A GitHub account** - Create one at [github.com/join](https://github.com/join)
2. **Git installed locally** - Check if you have it by opening Terminal/Command Prompt and typing `git --version`
3. **Git configured with your identity** - See [Happy Git Chapter 7](https://happygitwithr.com/hello-git.html)

**For R users:** I highly recommend the book [Happy Git and GitHub for the useR](https://happygitwithr.com/) by Jenny Bryan. Work through Chapters 1-8 to get set up properly.

**For everyone else:** GitHub's own [getting started guide](https://docs.github.com/en/get-started/start-your-journey/about-github-and-git) is excellent.

### Quick Check: Are You Ready?

Open your terminal/command prompt and run:

```bash
git --version
git config --global user.name
git config --global user.email
```

If these commands return values (not errors), you're ready to go!

---

## Learning Path

### Step 1: Explore GitHub's Web Interface

**Did you know you can edit files directly on GitHub's website?** This is perfect for:
- Quick README updates
- Adding comments or documentation - we use [issues](https://github.com/javirudolph/github-practice/issues/4)
- Learning the basics before using Git locally
- Check out one of the [issues](https://github.com/javirudolph/github-practice/issues/5) for instructions

**Try it now:**
1. Browse to any file in this repository (like [practice_script.md](https://github.com/javirudolph/github-practice/blob/main/practice_script.md))
2. Click the pencil icon (✏️) to edit
3. Make a small change
4. Scroll down and write a commit message describing your change
5. Click "Commit changes"

You just made your first commit! 🎉

### Step 2: Understanding Branches

**What is a branch?**  
A branch is a parallel version of your repository. It lets you experiment without affecting the main code.

A helpful practice: When collaborating or experimenting, create a feature branch instead of working directly on main.

**Why?**
- `main` stays clean and working
- You can experiment freely
- Multiple people can work on different features simultaneously and not overlap their changes
- Easy to discard failed experiments

**Branch Workflow:**
```
main branch (stable, working code)
    │
    ├── your-name-feature (your experimental work)
    │
    └── another-feature (someone else's work)
```



### Step 3: Your First Branch and Pull Request

Check out [this issue](https://github.com/javirudolph/github-practice/issues/6) and create a branch! Or follow [GitHub hello-world guide](https://docs.github.com/en/get-started/start-your-journey/hello-world) which walks you through:

1. **Creating a branch**
   - Click the branch dropdown (says "main")
   - Type a new branch name: `yourname-practice`
   - Click "Create branch"
   
2. **Making changes**
   - Edit [practice_script.md](https://github.com/javirudolph/github-practice/blob/main/practice_script.md)
   - Add your name and a comment about what you're learning
   - Commit your changes to your branch

3. **Opening a Pull Request (PR)**
   - Click "Pull requests" tab -> "New pull request"
   - Select your branch to merge into `main`
   - Write a description of what you changed and why
   - Click "Create pull request"

4. **Review and Merge**
   - The repository owner reviews your changes
   - If approved, your branch gets merged into `main`
   - You can safely delete your branch after merging

**Congratulations!** You've completed the basic GitHub workflow. 🎉

### Step 4: Practice Issues

Issues are GitHub's way to track tasks, bugs, and discussions.

**Try it:**
1. Go to the [Issues tab](https://github.com/javirudolph/github-practice/issues)
2. Find [Issue](https://github.com/javirudolph/github-practice/issues/9)
3. Follow the instructions to practice commenting

---

## Working with Branches: Common Scenarios

### Scenario 1: I want to try something without breaking my code

```bash
# Create and switch to a new branch
git checkout -b experiment-analysis

# Make changes, commit them
git add modified_file.R
git commit -m "Testing new statistical method"

# If experiment works: merge it
git checkout main
git merge experiment-analysis

# If experiment fails: abandon it
git checkout main
git branch -D experiment-analysis  # Delete the branch
```

### Scenario 2: I need to switch between tasks

```bash
# You're working on a feature
git checkout -b feature-visualization

# Urgent bug appears! Switch to main
git checkout main

# Fix bug on a new branch
git checkout -b hotfix-data-import
# ... make fixes ...
git checkout main
git merge hotfix-data-import

# Return to your feature work
git checkout feature-visualization
```

### Scenario 3: Keeping your branch updated with main

```bash
# You're on your feature branch
git checkout feature-analysis

# Update main branch
git checkout main
git pull origin main

# Bring main's updates into your branch
git checkout feature-analysis
git merge main
```

---

## Common Questions

**Q: What's the difference between Git and GitHub?**  
A: Git is the version control software that runs on your computer. GitHub is a website that hosts Git repositories and adds collaboration features.

**Q: When should I commit?**  
A: Commit when you complete a logical unit of work. Each commit should represent one focused change with a clear message. Commit often!
**Q: What makes a good commit message?**  
A: 
- Start with a verb: "Add", "Fix", "Update", "Remove"
- Be specific: ❌ "Update code" -> ✅ "Add error handling to data import function"
- Keep it under 50 characters for the first line
- Just give up and write your feelings... hey, it happens. I have multiple terrible commit messages like 'random', 'changes', etc. Don't recommend, but it happens, we try to do better.

**Q: I made a mistake in my last commit. Can I fix it?**  
A: Yes! If you haven't pushed yet:
```bash
# Fix the files, then:
git add fixed_file.R
git commit --amend --no-edit  # Adds to previous commit
```

**Q: How do I see what changed?**  
```bash
git status          # See which files changed
git diff            # See line-by-line changes
git log --oneline   # See commit history
```

---

## Additional Resources

General best practices [here](https://docs.github.com/en/repositories/creating-and-managing-repositories/best-practices-for-repositories)

### For R Users
- [Happy Git and GitHub for the useR](https://happygitwithr.com/) - Chapters 1-8 for setup
- [usethis package](https://usethis.r-lib.org/) - R package to streamline Git/GitHub workflow

### For Everyone
- [GitHub Documentation](https://docs.github.com/en/get-started/quickstart/hello-world)
- [GitHub Skills](https://skills.github.com/) - Interactive tutorials
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)

### Visual Learning
- [Visualizing Git](https://git-school.github.io/visualizing-git/) - See what Git commands do
- [Learn Git Branching](https://learngitbranching.js.org/) - Interactive branch tutorial

---

## Questions or Problems?

Open an [issue](https://github.com/javirudolph/github-practice/issues) and I'll help you out!

---

## About

This repository is maintained by Javi Rudolph, Computational Literacy Librarian at UF Libraries, and is designed to support computational literacy in ecology and natural resource management. 

For more resources on reproducible research in ecology, visit my [website](https://javirudolph.github.io) or check out my [other repositories](https://github.com/javirudolph).
