# Various ways to enter git rebase interactive mode.

Assuming that we have four commits.
```
> git log --oneline

0ab8c9e fix again
d6a5c92 fix more
4e9a158 fix
7bd20db first commit
```

We can enter the interactive mode by commit count. `git rebase -i HEAD~3`
```
> git rebase -i HEAD~3

pick 4e9a158 fix
pick d6a5c92 fix more
pick 0ab8c9e fix again

# Rebase 7bd20db..0ab8c9e onto 7bd20db (3 commands)
...
```

or, we can enter by (abbreviated) commit hash.
- `git rebase -i 4e9a158`
- `git rebase -i 4e9a158edf1326ed7fafcd2502ee1d41ea96a364`

```
> git rebase -i 4e9a158

pick d6a5c92 fix more
pick 0ab8c9e fix again

# Rebase 4e9a158..0ab8c9e onto 4e9a158 (2 commands)
```
**- Please note that it will start from the one above the commit hash we inputted.**

Jan 25, 2017 by jeongwooklee
