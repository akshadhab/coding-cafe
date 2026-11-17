# Lab 4 notes: Git & GitHub

## Question 1
`--global` saves the name and email in my user-level Git config (`~/.gitconfig`), so they apply to every repository on my computer. Without it, Git writes the setting only to the current repository's `.git/config`, so it would apply to that one repo, and the command fails if I am not inside a repository.

## Question 2
`ls -a` showed a hidden folder called `.git` (plus `.` and `..`) that plain `ls` hides because its name starts with a dot. Inside it Git keeps the whole repository: the commit history and objects, the branch and tag references, `HEAD`, and the repo's config.

## Question 3
Git listed everything in the folder as untracked: my lab notebooks, the data folder and the README, around ten entries. It also offered `.venv/`, which I did not write. That folder is the virtual environment and holds thousands of files of other people's library code.

## Question 4
After I created `.gitignore`, the `.venv/` entry disappeared from the untracked list, and so would `__pycache__/`, `.pyc` files and `.DS_Store`. A new entry, `.gitignore` itself, appeared, and my own lab files stayed in the list.

## Question 5
It should be committed. The ignore rules are part of the project, so anyone who clones the repository, or me on another computer, gets the same rules and does not commit `.venv/` by accident. If it were ignored, the rules would exist only on my laptop.

## Question 6
`README.md` moved from "Untracked files" to "Changes to be committed". In the three-places model it was copied from the working directory into the staging area (index), so it is lined up for the next commit but is not in the repository history yet.

## Question 7
Git printed the branch name, a short hash and my commit message, then a summary line with the number of files changed and insertions, followed by a `create mode` line for each new file. It reported every file I had staged as changed, since they were all new to Git.

## Question 8
They are the short (abbreviated) commit hash, the first seven characters of the full 40-character SHA-1 hash. The hash is the commit's unique ID, so I can use it to refer to that exact commit in commands like `git show`, `git diff` or `git checkout`.

## Question 9
1. Edit or create files in the working directory.
2. Run `git status` to see what changed.
3. Run `git add` to stage the changes.
4. Run `git commit -m "message"` to save them to the history.

## Question 10
`README.md` is a convention that tools and people both recognise: it is the first file a visitor is expected to read. GitHub looks for that exact name in the root of the repository and shows it on the front page, so it has to sit at the top level with that name to work as the project's introduction.

## Question 11
`gh auth login` signed me in through the browser and stored an access token for my GitHub account on my computer. It also set `gh` up as Git's credential helper, so when I push over HTTPS Git gets the token from `gh` automatically and never asks for a password.

## Question 12
The front page shows the list of files with the latest commit message, and below it the contents of `README.md` rendered as formatted text. GitHub automatically displays the README from the root folder because it is meant to be the introduction to the repository.

## Question 13
No. `git log --oneline` shows the same commits with the same hashes as before the push. Pushing only copied my commits to GitHub; the one visible difference is that the log now marks where `origin/main` is, on the same commit as my local `main`.

## Question 14
A private repository still exists on GitHub's servers with its full history; it is just hidden from everyone except me and the collaborators I invite, which is why the TAs can read it. If the repository did not exist on GitHub, the work would live only on my laptop, with nothing to share, no one able to review it, and no backup if the laptop failed.
