# ashley's `/git(hub)?/g` convention

Progress:

- [ ] commiting guide
- [x] commit message convention
- [ ] branch naming scheme
- [ ] pr naming scheme
- [x] github flow description
- [ ] how to prs guide
- [ ] how to issues guide
- [ ] why you should use the `github issue notebooks` vscode extension
- [ ] gh cli guide

## Table Of Contents

## commiting guide: `atomic commits`

---
---

## commit message convention: `hrcc`

`hrcc` is a commit message convention made by me, ashxi, in order to make a commit convention with the readability of putting whatever you want but the automatationability of the angular commit convention.

in this git convention, it will mostly be used for squash commits from a feature branch to the dev branch.

the syntax is as follows:

### message

- `type` message \[scope\]

for example:

- `add` hrrc explanation to \[readme\].md

also, if the commit is a pr commit,
make sure to add the pr to the end of the message as follows:

- `add` hrrc explanation to \[readme\].md { #2 }

### body

there are two types of bodies depending on whether you are doing a squash commit or hotfix commits.

hotfix:

```diff
explanation
explanation
etc...
```

squash:

```diff
+ commit messages from squash
+ commit 2
+ commit 3

explanation
```

### footer

there is only 3 footers:

- breaking changes (explained next): `!:`
- reviewers: `reviewers: @ashxi`
- notifications: `cc @ashxi`

### breaking changes

breaking changes in a commit are signified in two ways:

`<!>` at the beginning of the commit message.

`!:` in the footers to tell you what broke.

---
---

## branch naming scheme: `hrbc`

## pr naming scheme: `hrpr`

---
---

## github flow description

Github Flow is a lightweight, branch-based git workflow.

The main concepts I will be adressing here are these:

- the main (prod) branch
- the dev (develop) branch
- feature branches
- hotfix branches
- why we use squash when we do feature -> dev prs
- why we use merge when we use dev -> main prs

---

### main branch

the main branch in a github flow repository is `main`. it could also be called `master`, `trunk`, etc.

this branch is best described as the *production* branch.

whenever you make a pr from dev (main development branch) to this branch, you are essentially releasing a new version of your software.

what a version means is up to you.

whenever you release a new version, you tag it (`git tag` or github's web ui).

tagging also allows for easy CD.

---

### dev branch

the dev branch in a github flow repository is usually `dev`. it could also be called `develop`, `development`, `devel`, among other things.

this branch is best described as *the latest development version*.

all feature branches eventually end up squashed into here.

this is the only branch besides `main` who has `hrcc` commit histories.

this is also the only branch allowed to be merged into `main`.

---

### feature branches

these branches are the *pr branches*.

basically, these branches are the `from` in `from -> to`, where `to` is always `dev`.

the commits on these branches do not have to follow the `hrcc`, because when these are squash-commited, it will provide `hrcc` commits to the actual branches that have changelogs.

these branches are allowed allow to be squashed, and only into `dev`.

---

### hotfix branches

these branches are the branches that are used to fix important issues in the `main` branch.

essentially, if you accidentally push a very severe bug to `main`, you would use a hotfix branch in order to fix it.

a small explanatoin of a hotfix workflow:

- created off latest `main`
- only commits allowed on hotfix are about issue
- no feature enhancements or chores (`feat` or `chore` in *`hrcc`*)
- merges into both master & develop branches when its finished
- deleted after merge

---

### why squash for feature -> dev?

we use squash when we do feature -> dev because it allows for the commits inside of the pr's `feature` branch to be anything (the developer doesn't have to worry about commit conventions), and then when the pr is finished it gets squashed into dev as a `hrcc` commit.

if we didn't do this, it would require every developer to follow commit conventions and have to worry about all of that stuff. it's better for both ends.

instead of every commit having to be formatted correctly, they just make sure the pr is named correctly according to `hrcc` and then they're done.

for example, look at pr #1.

---

### why merge for dev -> main?

we use merge for dev -> main because of the fact that we only use squashes so the developers don't have to worry and it makes sense in the context of github flow.

we use merges, because of instead of squashing all of the new developer commits into one commit for main, we instead make the `main` branch be a snapshot of the latest production-ready (new-version-ready) `dev` branch, and tag the main branch for both CD purposes and to mark previous version releases.

---
---

## how to prs guide

## how to issues guide

## why you should use the `github issue notebooks` vscode extension

## gh cli guide
