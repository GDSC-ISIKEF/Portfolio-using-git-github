# Git & GitHub, Part Two: Code, Commit and Launch

Workshop by **GDSC ISIKEF** with **Mosaïque Club**.
Prepared by [Oussema Cherif](https://oussemacheriflinks.netlify.app/), Tech Lead at GDSC ISIKEF.

In Part 1 we learned the basics of Git and GitHub. In Part 2 we learn to write clean commits, work with issues, resolve merge conflicts, and then build and publish a personal portfolio.

## Agenda

1. Recap of Part 1
2. Writing good commit messages (`feat(scope): description`)
3. Issues
4. Merge conflicts
5. Practice: build your portfolio, one commit per step
6. Deploy with GitHub Pages

## Slides

- [Part 2 slides (PDF)](git-github-part2.pdf)

## Before you come

- A GitHub account
- [Git](https://git-scm.com/downloads) installed (`git --version` should work)
- [VS Code](https://code.visualstudio.com/) with the **Live Server** extension
- Git configured:
  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "you@example.com"
  ```

## Commit convention

```
type(scope): description
```

| Type | Use it for |
| --- | --- |
| `feat` | a new feature or visible addition |
| `fix` | a bug fix |
| `docs` | documentation only |
| `style` | formatting or CSS, no logic change |
| `refactor` | restructure code, same behavior |
| `chore` | setup, config, tooling |

Rules: lowercase, imperative ("add", not "added"), under 50 characters, no final period.

## The portfolio practice

The portfolio is built from small files. `index.html` loads every file in `parts/`, so each step is one new file and one commit.

```
portfolio/
├── index.html
└── parts/
    ├── hero.html
    ├── about.html
    ├── skills.html
    ├── projects.html
    └── contact.html
```

| Step | File | Commit message |
| --- | --- | --- |
| 1 | `index.html` | `chore(setup): add html skeleton and base styles` |
| 2 | `parts/hero.html` | `feat(hero): add intro with name and role` |
| 3 | `parts/about.html` | `feat(about): add about me section` |
| 4 | `parts/skills.html` | `feat(skills): add skills list` |
| 5 | `parts/projects.html` | `feat(projects): add project cards` |
| 6 | `parts/contact.html` | `feat(contact): add contact links and footer` |

Step 6 is done with an issue, a branch (`feat/contact`) and a pull request that says `Closes #1`.

For each step: save the file, check the page, then

```bash
git add parts/hero.html
git commit -m "feat(hero): add intro with name and role"
git push
```

### Run it locally

Open the `portfolio` folder in VS Code, right-click `index.html` and choose **Open with Live Server**.
Opening `index.html` by double-click shows a blank page, because browsers block loading the parts from local files.

## Deploy with GitHub Pages

1. Make the repository **Public**.
2. Go to **Settings**, then **Pages**.
3. Under **Source**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then **Save**.
4. After about a minute, your site is at `https://<username>.github.io/<repository>/`.

Every push to `main` updates the site.

## Useful links

- [Conventional Commits](https://www.conventionalcommits.org)
- [GitHub Pages documentation](https://docs.github.com/en/pages)
- [Oussema Cherif, all my links](https://oussemacheriflinks.netlify.app/)