# GitHub Desktop Instructions for Claude

**Important:** The user uses GitHub Desktop on their MacBook for git operations.

## When instructing the user about git operations:

### ✅ DO provide GitHub Desktop instructions:
- "In GitHub Desktop, create a new branch called..."
- "In GitHub Desktop, commit your changes with message..."
- "In GitHub Desktop, push to origin"
- "In GitHub Desktop, create a pull request by clicking 'Create Pull Request'"

### ❌ DON'T provide command-line git instructions:
- ~~"Run `git checkout -b branch-name`"~~
- ~~"Run `git commit -m 'message'`"~~
- ~~"Run `git push origin branch-name`"~~

## Common GitHub Desktop Workflows

### Creating a Branch
1. Click "Current Branch" dropdown at the top
2. Click "New Branch"
3. Enter branch name
4. Click "Create Branch"

### Committing Changes
1. Review changes in the "Changes" tab
2. Check the files you want to commit
3. Write commit message in the summary field
4. Click "Commit to [branch-name]"

### Pushing to Remote
1. After committing, click "Push origin" button at the top
2. If it's a new branch, it will prompt to publish

### Creating a Pull Request
1. After pushing, click "Create Pull Request" button
2. GitHub will open in browser
3. Fill in PR details and click "Create pull request"

### Merging a Pull Request
1. Go to GitHub.com pull requests page
2. Review changes
3. Click "Merge pull request"
4. Confirm merge

### Syncing/Pulling Latest Changes
1. Click "Fetch origin" to check for updates
2. If updates exist, click "Pull origin" to download them

---

*When working with the user, always provide GitHub Desktop instructions rather than command-line git commands.*
