# Odeus

Odeus is a small Python utility for creating dated Git commits in a repository
you own or are authorized to modify. It appends a line to a file, creates
commits with dates from the previous year, and pushes them to that repository's
configured remote.

The public `odeus` repository contains the tool. Each user supplies a separate
local clone of their own target repository when the program runs.

## Requirements

- Python 3
- Git installed and configured
- Permission to push to the target repository
- A target repository cloned to your computer

## Install the tool

Clone this repository:

```bash
git clone https://github.com/vatsalkoriya/odeus.git
cd odeus
```

## Prepare your target repository

Clone a repository that you own or have permission to update. Replace the URL
with your own repository URL:

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
```

For example:

```bash
git clone https://github.com/vatsalkoriya/odeus-trial-auto.git
```

Make sure Git authentication works and that the target repository has a
configured `origin` remote.

## Run Odeus

From the `odeus` folder, run:

```bash
python main.py
```

Answer the prompts:

1. **Number of commits** — defaults to `20`
2. **Repository path** — the local folder of your target repository, not its
   GitHub URL
3. **File to update** — defaults to `data.txt`

Example:

```text
Number of commits [20]: 3
Repository path [.]: C:\Users\YourName\projects\my-repository
File to update [data.txt]:
```

The program appends one line to the selected file, creates each commit, and
pushes the commits to the target repository with `git push`.

## Important notes

- Do not enter a URL at the repository-path prompt. Clone the repository first
  and enter its local folder path.
- Use only repositories you own or are authorized to modify.
- GitHub may count commits only when the commit email is associated with your
  GitHub account and the commits are pushed to a recognized branch.
- Backdated commits should not be used to misrepresent real work or activity.
