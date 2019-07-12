# Fixup commit and auto squash.

Assuming that we have three commits.
```
> git log --oneline

23ba44f New Feature 2
d9ba33f New Feature 1
aa0a735 Some old feature commit
```

Oh, I found typo from the `d9ba33f New Feature 1` commit.
Let's fix the commit up!
```
..after fixing

> git add --a
> git commit --fixup d9ba33f
[dev 691d411] fixup! New Feature 1
```

Notice that commit name `fixup! New Feature 1` has been added automatically.
```
> git log --oneline

691d411 fixup! New Feature 1
23ba44f New Feature 2
d9ba33f New Feature 1
aa0a735 Some old feature commit
```

Let's add more fixup commits.
```
> git log --oneline

5a28cff fixup! New Feature 1
40ea730 fixup! New Feature 1
691d411 fixup! New Feature 1
23ba44f New Feature 2
d9ba33f New Feature 1
aa0a735 Some old feature commit
```

Now, it's time to use `--autosquash` option!
```
git rebase -i HEAD~5 --autosquash
```

interactive rebase editor will be opened with `fixup` command.
```
pick d9ba33f New Feature 1
fixup 691d411 fixup! New Feature 1
fixup 40ea730 fixup! New Feature 1
fixup 5a28cff fixup! New Feature 1
pick 23ba44f New Feature 2

# Rebase aa0a735..5a28cff onto aa0a735 (5 commands)
```

The only thing we need to do is just save & quit.
Tada! :tada: :tada:
```
> git log --oneline

f82b41a New Feature 2
4397271 New Feature 1
aa0a735 Some old feature commit
```

Mar 10, 2017 by jeongwooklee
