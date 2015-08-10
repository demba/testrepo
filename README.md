# Git forkflow notes

    git checkout

One can either checkout a `file` or a commit `d3dadaw` in the commit history of the project. There are notable differences between these two processes.

## checkout on a `file`

When one checks out a file from a previous commit, the file replaces its counterpart in and is put in the staging area. This means that one can modify the file, `git add` and `git commit` to record any changes as part of the project history. To discard any changes, one must `git reset` and checkout a fresh version from `master`, or do a `git reset --hard`.

## using checkout on a `file` with `reset`

If changes made to the file that was checked out have been staged *but not commited*, then one must unstage them first using `git reset`, followed by a `git checkout file` to revert to the latest committed version of the file. If the changes have already been committed, one needs to reset to an older commit and checkout the version of the file from the latest commit, or the one that is desired.

N.B.: Perhaps this can be solved by branches and merging when I read about that.

P.S.: `reset` basically unstages and/or uncommits (*local changes*), which can be followed by a checkout in a straightforward way, or simply a hard reset.

There is a nice example on the [Atlassian tutorial](https://www.atlassian.com/git/tutorials/undoing-changes/git-reset) page.


## checkout on a `commit`

The whole of the current directory is made to look like what it did at the time of said commit. Any changes made to files here cannot be part of the current branch's history. A new branch must be created to record the changes, and then a `merge` of some kind done to incorporate the changes into `master`. One can also `stash` any changes made `checkout master` to recover the project at the state of the latest commit.

N.B.: A nice feature here is that `git` will not let you check out a previous commit unless any changes since the latest commit have been staged and committed!

# Collaboration workflows

## Establishing connections to remote repos

In git, you have access to a dedicated *local* version-controlled development environment. You can pull from/push to other non-local repositories using the `git remote` command

`git remote -v`: list all remote connections with url

`git remote add`

`git remote rm`

`git remote rename`

## Looking at remote changes before incorporating locally

The `git fetch` commands allows you to look at changes from a(ll) branch(es) before incorporating them in one's local repo.

`git fetch <remote>`

`git fetch <remote> <branch>`

## Incorporating `remote` changes locally using `git pull`

`git pull remote` does the same thing as a `git fetch` followed by a `git merge`. So it fetches changes to remote branches, without intengrating them right away into the local repo. It follows this by merging remote branches into local ones.

### Rebasing

Rebasing is a way to ensure a **linear** commit/change history. It's basically saying "I'd like to put my changes on top of everybody else's". It's so common that a way to automatically build it into one's workflow is

`git config --global branch.autosetuprebase always`

`git pull --rebase`

`git checkout master &&
git pull --rebase origin`

There's a way of 'cleaning-up' one's changes first with a interactive `rebase` before pushing them. More about rebasing [here](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase-i/)!

Basically, you create a new branch from master, do your thing, maybe make changes to master along the way, you checkout the new branch, rebase it from master, checkout master and do a fast-forward merge.

## Sharing local changes with `remote` using `git push`

`git push <remote> <branch>`

`git push <remote> --all`

Yo yo yo

  ```
  git checkout master
  git fetch origin master
  git rebase -i origin/master
  # Squash commits, fix up commit messages etc.
  git push origin master
  ```


## Branching

`git branch -r` lets you see which branches you might see after fetching from a `remote`.

Note that one refers to remote branches as `<remote>/<master>`, so that all commands that accept a local branch can work with this syntax.

# testrepo

## This is a nested list

1. In the beginning
  1. There was nothing
  2. And then, there was something
2. In the end
  1. There will be something
  2. And then, perhaps, nothing.


  ## This is a block of code, inside a two-level list

  ```
  for i in range(10):
    print i**2
  ```

> "Do you have time to meet?" That's what she asked.
>
> A block quote with two paragraphs.

[Visit Dataholiks!](http://dataholiks.com)

<table>
    <tr>
        <td>Foo</td>
        <td>Yoyo</td>
    </tr>
    <tr>
        <td>Hey hey hey...</td>
        <td>Good byyyee!!</td>
    </tr>
</table>

Made this edit in tstrp1, and pushed. Then made edit in tstrp2 to see what happens (merge)!

Potential conflict here with two different versions of the file!

Conflict resolved!!
