Git tips and tricks

Person 1: "Git is too hard, i prefer svn"
Person 2: "git gud"
Person 1: "No"
Person 2: "sudo git gud"

- oh-my-zsh git aliases and `alias | grep <git-term>` 
    - can add to bash as well

- History
    - Linus Torvalds, made for Linux (replacement for Perforce)
    - distributed (centralized: network checkout)

Concepts
- <https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell>
- working tree
- index
- remotes
- explore .git

- Useful git config aliases (brad and bradr, lg, ru, suir)

- git config should-haves

    git config --global fetch.prune true
    git config --global merge.conflictstyle = diff3
    git config --global diff.colorMoved = zebra
    git config --global diff.colorMovedWS = allow-indentation-change
    git config --global log.follow true
    git config --global pull.rebase true

- git command niceties
    - `git checkout -` switches to your previous branch - same with `git merge -` and some others (`-` means `@{-1}`, where `HEAD` last pointed to)
    - `git diff --word-diff` (`gdw`) - Useful for textual reviews on command line
        - works for `git show` too
    - `git add -p` / `checkout` / `reset` / ...others
    - `git reset` - move branches to wherever they should go
        - <https://git-scm.com/book/en/v2/Git-Tools-Reset-Demystified#_recap>
        - Throw away local branch to get back on remote
            - `git reset --hard origin/my-feature-branch`
        - undo commit (preserve working tree)
            - `git reset HEAD^`
        - undo all stages (make index like working tree)
            - `git reset`
        - Get everything back to a fresh commit checkout
            - `git checkout HEAD .`
    - `git commit -am "My message"` vs `git add -u` vs `git add .`
    - Deserves to be mentioned: `git switch`, `git restore`
    - stashes
    - Rebases/merge
        - First off: `--abort`
        - Rebase: default is comparable to series of git cherry-pick
        - interactive

- mention VS Code "Files: Auto Save" -> "onWindowChange"
