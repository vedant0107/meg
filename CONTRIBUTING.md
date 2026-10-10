# How we work together

Five of us share this repository. These steps keep us from overwriting each other's work.

The one rule that matters most: **nobody commits directly to `main`.** Everyone works on their own branch and merges through a pull request (PR).

## One-time setup

1. Install Git from https://git-scm.com and create a GitHub account.
2. Ask the repository owner to add you as a collaborator, then accept the email invitation.
3. Tell Git who you are. Use the email from your GitHub account:

   ```
   git config --global user.name "Your Name"
   git config --global user.email "you@example.com"
   ```

4. Download the project:

   ```
   git clone https://github.com/saiingale9067/MEGATHON.git
   cd MEGATHON
   ```

The first time you push, a GitHub sign-in window opens. Sign in there. Never type a password or token into a file in this project.

## Every time you start a piece of work

1. Get the latest `main`:

   ```
   git switch main
   git pull
   ```

2. Create your own branch. Name it `feature/` plus a short description:

   ```
   git switch -c feature/commons-api-fetch
   ```

3. Do your work. Save your progress often with small commits:

   ```
   git status
   git add path/to/file.py
   git commit -m "Fetch categories for a file from the Commons API"
   ```

   Run `git status` before `git add` so you know exactly what you are about to commit.

4. Upload your branch. The first push needs the extra options; after that, `git push` is enough:

   ```
   git push -u origin feature/commons-api-fetch
   ```

5. Open a pull request. Go to the repository on GitHub, click **Compare & pull request**, describe what you changed, and click **Create pull request**.

6. Ask one teammate to read it. When they approve, click **Merge pull request**, then **Delete branch**.

7. Go back to step 1 for your next piece of work.

## If `main` changed while you were working

Bring the new changes into your branch before you open the PR:

```
git switch main
git pull
git switch feature/commons-api-fetch
git merge main
```

If Git reports a **conflict**, it means you and a teammate edited the same lines. Open the file, look for the `<<<<<<<`, `=======` and `>>>>>>>` markers, keep the correct version, delete the markers, then:

```
git add path/to/file.py
git commit
```

If you are unsure, stop and ask the teammate who wrote the other change. Do not guess.

## Team rules

- One branch per task. Keep branches short-lived: merge within a day or two.
- Agree who is working on which files, so two people are not editing the same file.
- Never use `git push --force`.
- Never commit passwords, API keys, tokens or `.env` files.
- Do not commit datasets or trained models. Put them in `data/`, which Git ignores, and share them through a drive link.
- If something looks wrong, ask in the team chat before running commands you found online.

## Where things go

| Folder | What belongs there |
|---|---|
| `src/` | The project's source code |
| `tests/` | Automated tests for the code in `src/` |
| `notebooks/` | Jupyter notebooks for experiments. Put your name in the file name. |
| `data/` | Local datasets and model files. Ignored by Git. |
| `docs/` | Design notes, diagrams and presentation material |
