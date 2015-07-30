# Git forkflow notes

    git checkout

One can either checkout a `file` or a commit `d3dadaw` in the commit history of the project. There are notable differences between these two processes.

## checkout on a `file`

When one checks out a file from a previous commit, the file replaces its counterpart in and is put in the staging area. This means that one can modify the file, `git add` and `git commit` to record any changes as part of the project history. To discard any changes, one must `git reset` and checkout a fresh version from `master`.

## checkout on a `commit`

The whole of the current directory is made to look like what it did at the time of said commit. Any changes made to files here cannot be part of the current branch's history. A new branch must be created to record the changes, and then a `merge` of some kind done to incorporate the changes into `master`


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

> "Do you have time to meet?" That's what the b*tch said.
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
