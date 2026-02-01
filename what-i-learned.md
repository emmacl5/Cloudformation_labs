## What I learned from publishing this repo

### Git basics

- `git init` created a local Git repository in my folder.
- `git status` helped me see what Git was (and wasn’t) tracking.
- Files are "untracked" until I stage them with `git add`.
- `git add .` staged all files in the folder.
- `git commit` created my first snapshot of the project history.

### GitHub + remotes

- A "remote" is a link from my local repo to GitHub.
- I can see my remotes using `git remote -v`.
- "Repository not found" usually means the remote URL is wrong or the repo doesn’t exist.
- My push failed because my GitHub username in the URL was misspelled.
- I fixed it using:
  - `git remote set-url origin <correct-url>`
- `git push -u origin main` uploaded my code and set `main` to track GitHub.

### CloudFormation learning

- I created a simple CloudFormation template that declares AWS resources in YAML.
- I learned that hard-coding an S3 bucket name and AMI makes the template non-portable:
  - bucket names must be globally unique
  - AMIs are region-specific
