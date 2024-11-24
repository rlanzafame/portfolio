# Robert's Teaching Portfolio

A collection to share my teaching materials and activities, each of which can be found as an "item" at `rlanzafame.github.io/portfolio/<ITEM>`. The purpose is to facilitate sharing, especially when materials are hard to extract from their original education context (e.g., password-protected, difficult to find, etc). At the moment this is just a collection without description or explanation (work in progress).

The best way to view the contents of the portfolio is to start here: [rlanzafame.github.io/portfolio](https://rlanzafame.github.io/portfolio).

## Design and Configuration

My goal for this repository is to be simple to maintain (i.e., dumping static files in a subdirectory and letting GitHub do the rest). I also wanted to have the following file system structure, where the materials are accessed at `https://rlanzafame.github.io/portfolio/<ITEM>`, but the repository itself stays simple by putting the source in a subdirectory `./portfolio/`, which will allow for scripts and simple workflows to be added on an as-needed basis.

```
portfolio/
|--- README.md
|--- a few miscellaneous files (e.g., scripts, .gitignore)
|---portfolio/
    |--- index.html
    |--- item-01/
         |--- index.html
         |--- ...
    |--- item-02/
    |    ...
    |--- item-n?
```

### Landing Page

The landing page is a simple HTML file `./portfolio/index.html`.

When new material is added to the portfolio, add a row to the table.

### Deploy Website

The subdirectory `portfolio` contains all of the source files for the website items. To achieve the desired URL structure the contents of `portfolio` are pushed directly to the `gh-pages` branch. This is enabled in the "Pages" part of the repository settings by selecting "Deploy from a branch" as source with branch `gh-pages` and folder `/ (root)`. 

This is the command to update the website, which should be run from the root of the repository on the main branch.

```git
git subtree push --prefix portfolio origin gh-pages
```

[This gist](https://gist.github.com/cobyism/4730490) helped me with the `git subtree` solution.