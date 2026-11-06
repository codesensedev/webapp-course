# 1.3: The head, the body and a button

About 15 minutes.

By the end of this lesson, your browser tab will show a graduation cap and say **Student Planner**, and your page will have a plain **Continue** button under the welcome line. You will know which part of the HTML describes the page and which part holds what you can see.

```text
+--------------------------------------------+
| [cap] Student Planner                   x  |  <- icon and title are in the head
+--------------------------------------------+
|                                            |
|              Student Planner               |  <- the page is in the body
|                Welcome, Sam                |
|               [ Continue ]                 |
|                                            |
+--------------------------------------------+
```

## The idea

An HTML page has two main parts:

```text
  <head>  information about the page
      the tab title, favicon and link to the CSS file

  <body>  the page itself
          the heading, welcome line and button
```

The browser shows the title in its tab, not in the page. The things you want people to see go in the `body`.

A **favicon** is the small image shown beside a page's title in the browser tab. The `head` links to the image file; the image itself lives next to `index.html`.

A button has a plain look from the browser, even before you write any CSS for it. It will not do anything when clicked yet. You will give it a job in a later lesson.

## Steps

### 1. Start from last time

Open your project in VS Code. Open `index.html`. It should have a `head` with a `title` and a link to `style.css`, and a `body` with your heading and welcome line. Make sure Go Live is running.

Your `head` should look like this. The title still says `Document`:

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="style.css">
</head>
```

### 2. Give the page a title

In the `head`, change `Document` to `Student Planner`:

```html
<title>Student Planner</title>
```

Save `index.html` and look at the browser tab.

You should see: the tab says **Student Planner**. The words on the page have not changed. The title describes the page to the browser; it is not page content.

### 3. Add a graduation-cap favicon

In File Explorer, open the course's `lessons/assets` folder. Copy [favicon.svg](assets/favicon.svg) into your `studentplanner` folder, next to `index.html` and `style.css`.

In the `head` of `index.html`, add a link to the icon under the link to `style.css`:

```html
<link rel="stylesheet" href="style.css">
<link rel="icon" type="image/svg+xml" href="favicon.svg">
```

Save `index.html` and look at the browser tab. If the icon does not appear right away, refresh the page.

You should see: a small graduation cap beside **Student Planner** in the tab.

### 4. Find the page itself

In `index.html`, find the opening `<body>` and closing `</body>` tags. The heading and welcome line are between them. That is the page content the browser shows.

The `head` comes before the `body`. The link to `style.css` belongs in the `head`, but the things you want to see belong in the `body`.

### 5. Add a button

Under the welcome paragraph, add a button that says `Continue`:

```html
<body>
    <main>
        <h1>Student Planner</h1>
        <p>Welcome, Sam</p>
        <button>Continue</button>
    </main>
</body>
```

Keep your own name in the welcome line. Save and look at the browser.

You should see: a plain button under the welcome line. The browser gives it a default look, just as it gave the heading a default look in lesson 1.1.

Click the button. Nothing happens yet. It is a button on the page, but it does not have a job until a later lesson.

### 6. Check your file

Compare your `index.html` with this. Keep the name in your welcome line:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Planner</title>
    <link rel="stylesheet" href="style.css">
    <link rel="icon" type="image/svg+xml" href="favicon.svg">
</head>
<body>
    <main>
        <h1>Student Planner</h1>
        <p>Welcome, Sam</p>
        <button>Continue</button>
    </main>
</body>
</html>
```

You should see: the tab says **Student Planner**, and the page has the heading, your welcome line and the plain Continue button.

### 7. Save it with git

Finish with the routine from G2 and G3. Use the caption `1.3 Page title, favicon and button`:

```
git status
git diff
git add .
git commit -m "1.3 Page title, favicon and button"
git log --oneline
git push
```

You should see: `1.3 Page title, favicon and button` at the top of the log, and on GitHub after the push. In the Source Control tab it works the same way.

## Recap

- The `head` holds information about the page, including its tab title and its link to the stylesheet.
- The favicon is a small image linked from the `head`; its file sits next to `index.html`.
- The `body` holds the content that appears on the page.
- The browser shows the `title` in its tab, not in the page.
- The browser gives a button a plain default look. It does nothing until you give it a job.

## Homework

Each should take about five minutes. Finish with the routine and the caption `1.3 Homework`.

1. **Your page title.** Change the title to a name that suits your project. You know it worked when the new name appears in the browser tab.

2. **Your button words.** Change `Continue` to another short label that could fit your app. You know it worked when the new words appear on the button.

3. **Stretch: spot the two parts.** Point to the `head` and the `body` in your file. Name one thing in the `head` and one thing in the `body`. You know it worked when you can explain which one appears in the tab and which one appears on the page.

## Stuck?

- **The tab still says `Document`.** Check that you changed the text between `<title>` and `</title>` in the `head`, then save `index.html`.
- **The title appears on the page instead of the tab.** The title belongs between `<head>` and `</head>`, not between `<body>` and `</body>`.
- **The button does not appear.** Check that the whole `<button>Continue</button>` line is between `<body>` and `</body>`, then save and look at the browser.
- **The cap icon does not appear.** Check that `favicon.svg` is next to `index.html` and that the link in the `head` says `href="favicon.svg"`. Refresh the page, or close and reopen its tab.
- **The button looks plain.** That is expected. The browser gives it a default look; styling comes in a later lesson.
- **The page did not update.** Check that Go Live is running. You can also refresh the browser by hand: F5, or Cmd+R on a Mac.
