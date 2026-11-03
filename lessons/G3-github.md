# G3: GitHub

About 18 minutes. Do this after G2.

By the end of this lesson your project will be on GitHub: a copy of your files and all your save points, which your teacher can see. The routine you learned in G2 also gets a sixth move, `git push`.

Before you start you need a GitHub account. If you do not have one yet, tell your teacher.

## The idea

So far your save points live only on your computer. If the computer breaks, they are gone, and nobody else can see your work.

GitHub is a website that keeps a copy for you:

```
  your computer                         GitHub, the website
  +--------------------+     push      +--------------------+
  | studentplanner     | ------------> | studentplanner     |
  | (your save points) |               | (a copy)           |
  +--------------------+               +--------------------+
```

Git and GitHub are different things. Git is the tool on your computer that makes save points. GitHub is a website that stores git projects.

New words:

- **remote**: a copy of your project kept somewhere else. The usual nickname for it is `origin`.
- **push**: send your new save points to the remote.

## Steps

### 1. Make the project on GitHub

In your browser, go to github.com and sign in. Click the **+** at the top right and choose **New repository**.

- Name it `studentplanner`.
- Choose **Private**, so only you and the people you invite can see it.
- Leave everything else empty: no README, no `.gitignore`, no license. Your project already has a README.

Click **Create repository**.

You should see: a nearly empty page with a web address that ends in `.git`. Copy it with the copy button. It looks like this, with your own user name:

```
https://github.com/yourname/studentplanner.git
```

### 2. Share it with your teacher

On the repository page, open the **Settings** tab, choose **Collaborators**, and click **Add people**. Type your teacher's GitHub user name. Your teacher will tell you what it is.

You should see: your teacher's name in the list, waiting for them to accept. GitHub moves buttons around from time to time, so the names may be a little different.

### 3. Tell git where the copy lives

Back in the VS Code terminal, run this with the address you copied:

```
git remote add origin https://github.com/yourname/studentplanner.git
```

Then check it:

```
git remote -v
```

You should see:

```
origin  https://github.com/yourname/studentplanner.git (fetch)
origin  https://github.com/yourname/studentplanner.git (push)
```

### 4. Send your save points

```
git push -u origin main
```

The first time, a window may open and ask you to sign in to GitHub. Sign in and allow it.

You should see something like this. The numbers will differ, and the important line is `main -> main`:

```
Enumerating objects: 15, done.
Counting objects: 100% (15/15), done.
Delta compression using up to 8 threads
Compressing objects: 100% (11/11), done.
Writing objects: 100% (15/15), 2.10 KiB | 2.10 MiB/s, done.
Total 15 (delta 2), reused 0 (delta 0), pack-reused 0
To https://github.com/yourname/studentplanner.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
```

The `-u` tells git to remember where `main` goes. From now on you only need to type `git push`.

### 5. Look at it on GitHub

Reload the repository page in your browser.

You should see: your files, and your README shown underneath them as the front page of the project.

```
+--------------------------------------------------------+
| yourname / studentplanner                      Private |
+--------------------------------------------------------+
| main            4 Commits                              |
+--------------------------------------------------------+
| README.md     Add a line to README          2 days ago |
| index.html    Change the welcome word       1 hour ago |
| style.css     1.1 Hello: HTML and CSS       1 hour ago |
+--------------------------------------------------------+
| README.md                                              |
|                                                        |
| Student Planner                                        |
| A planner for my schedule, homework and activities.    |
| By Sam                                                 |
+--------------------------------------------------------+
```

Your page will look a little different, but it has the same parts. Click the number of commits. You will see the same captions that `git log --oneline` shows.

### 6. The routine, with a push

Now try the whole routine. Open `index.html` and change the welcome line again, for example to `Hi, Sam`. Save the file. Then:

```
git status
git diff
git add .
git commit -m "Try a push"
git log --oneline
git push
```

You should see: `git push` ends with a line like this, with different codes:

```
To https://github.com/yourname/studentplanner.git
   dcf142c..7fb3ed6  main -> main
```

Reload the repository page. The newest commit is now "Try a push".

In the Source Control tab it works the same way. After you commit, the blue **Commit** button turns into a **Sync Changes** button with an arrow and a number. Click it to push. VS Code may ask you to confirm.

From now on, every lesson ends with these six moves:

```
  1. git status
  2. git diff
  3. git add .
  4. git commit -m "lesson number and name"
  5. git log --oneline
  6. git push
```

A push only sends save points. If you changed a file but did not commit it, it is not on GitHub.

## Recap

- GitHub keeps a copy of your project, so it is safe and your teacher can see it.
- `git remote add origin <address>` tells git where the copy lives. You only do that once.
- `git push` sends your new save points. Do it at the end of every lesson.
- `git push` sends commits only. Commit first.

## Homework

Each should take about five minutes.

1. **Push your homework.** If you have not done the homework from lesson 1.1, do it now. Save it with the routine, with the caption `1.1 Homework`, and push. You know it worked when GitHub shows `1.1 Homework` at the top of the commits.

2. **Read a commit on GitHub.** On GitHub, click the commits, then click the one called `Change the welcome word`. You will see the same red and green diff you saw in VS Code. You know it worked when you can say what that commit changed.

3. **Stretch: a better README.** Add this to your `README.md`, with your own items:

   ```
   ## What I am learning

   - HTML
   - CSS
   - Git
   ```

   Commit it, push it, and reload GitHub. You know it worked when the README shows a heading and a bulleted list, not the `##` and `-` characters.

## Stuck?

- **`fatal: remote origin already exists`.** You have already added the remote. Run `git remote -v` to see the address. If the address is wrong, run `git remote set-url origin <the right address>`.
- **`error: src refspec main does not match any`.** Your timeline has a different name, or you have not saved anything yet. Run `git status`. If it says `master`, run `git branch -M main` and push again, and tell your teacher.
- **`Authentication failed` or `Permission denied`.** GitHub does not know it is you. Tell your teacher.
- **`Updates were rejected because the remote contains work that you do not have locally`.** You made the repository with a README or other file in it. Tell your teacher.
- **GitHub looks the same after the push.** Reload the page, and check that you committed before you pushed.
