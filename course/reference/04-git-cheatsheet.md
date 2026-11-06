# Git cheatsheet

The git commands from G1, G2 and G3 on one page. The letters in brackets say which lesson to look at.

## The picture

```
  files --git add--> frame --git commit--> save points --git push--> GitHub
```

- **add** puts changed files in the frame.
- **commit** takes the photo: a save point with a caption.
- **push** sends your save points to GitHub.

## Once per project

```
git init                              start watching this folder      (G1)
git remote add origin <address>       tell git where the copy lives   (G3)
git push -u origin main               the first push, to set it up    (G3)
```

## After every lesson: the routine

```
git status                what changed?                            (G1)
git diff                  what exactly changed?                    (G2)
git add .                 put everything that changed in the frame (G2)
git commit -m "words"     take the photo, with a caption           (G2)
git log --oneline         check the new save point is there        (G2)
git push                  send it to GitHub                        (G3)
```

The caption is the lesson number and its name, like `1.2 Colour and type`.

## Looking around

```
git --version             is git installed?                        (G1)
git status                what changed? what is saved?             (G1)
git diff                  the changes in files git already knows   (G2)
git log --oneline         your save points, newest first           (G2)
git remote -v             where does the copy live?                (G3)
```

If the log does not end by itself and you see a `:`, press `q`.

## Saving one file

```
git add <file>            put just one file in the frame           (G1)
```

Use it instead of `git add .` when you only want to save one file. Then commit as usual.

## Undo

```
git restore <file>        take a file back to its last save point  (G2)
```

Be careful. This throws away every change in that file since the last save point, and git cannot give them back.

## In VS Code: the Source Control tab

Open it with the icon with the branching line, or Ctrl+Shift+G.

```
  in the terminal            in the Source Control tab
  -----------------------    ---------------------------------------
  git status                 the lists: Changes and Staged Changes
  git diff                   click a file to see the diff
  git add .                  the + next to Changes
  git commit -m "words"      type the words in the box, click Commit
  git push                   the Sync Changes button
  git restore <file>         the Discard Changes icon
```

## When something goes wrong

- `fatal: not a git repository`: the terminal is not in your project folder, or you have not run `git init`.
- `no changes added to commit`: you skipped `git add`. Add the file, then commit again.
- `Author identity unknown`: git does not know your name yet. Tell your teacher.
- `fatal: remote origin already exists`: the remote is already set. Check it with `git remote -v`. To fix a wrong address, run `git remote set-url origin <the right address>`.
- `error: src refspec main does not match any`: your timeline has a different name, or you have not saved anything yet. Run `git status`. If it says `master`, run `git branch -M main`, push again, and tell your teacher.
- `Authentication failed` or `Permission denied`: GitHub does not know it is you. Tell your teacher.
- `Updates were rejected because the remote contains work that you do not have locally`: tell your teacher.

## Words

- **repository**: a project folder that git is watching.
- **commit**: a save point, and also the act of making one.
- **staged**: in the frame, ready to be committed.
- **diff**: the difference between your file now and the file at the last save point.
- **log**: the list of your save points.
- **remote**: a copy of your project kept somewhere else. Its usual nickname is `origin`.
- **push**: send your new save points to the remote.
