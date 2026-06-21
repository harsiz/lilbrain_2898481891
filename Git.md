Git is a [[version control]] system for code created by Linus Torvalds (the lead developer of [[Linux]] kernel.)

Some good commands to know:


### Stages
There are 3 stages that files are in while using git.

**Untracked**: The file exists but isn't a part of Git's version control system.

**Staged:** The file IS part of Git's version control BUT no changes have been committed to a git repo yet.

**Committed**: The file has been committed (appended) to a Git repo.

## Commands:

`git log` >> shows a list of all prior commits and their [[SHA-2]] hash.
 -  Ontop of that, you can truncate results if a lot of commits have been made using `git --no pager log -n [number]`
 - `--no-pager` means no interactive cli where u can scroll thru
   `-n` just the number of the most recent commits
 - `--graph` shows a cool ASCII graph that is.. not very readable
 - `--oneline` simplifies the long `git log` into a truncated "mini version" which is much easier to read. (Usually you'd be using `git log --oneline` instead of traditional `git log` unless you explicitly need the full [[SHA-2]] hash.)

`git add <file>` >> adds the file's recent changes so that it is staged and ready to be commited.

`git commit -m "message"` >> commits the files that have been staged providing a message for context.

## Git Objects

Git hashes are stored within a hidden file `.git/objects/[ab]/cdef012345678...`.
-  (`ab` is a placeholder for the first 2 characters in the hexadecimal hash)
- `cdef...` are the remaining characters.

You can NOT just use `cat` on them as it's compressed to bytes when trying to view it.
_instead_ you can use `xxd` which gets the hexadecimal out of the file.

You can also use `git cat-file` which just accurately concatenates the file for you, no need to faff around with the bytes and stuff.

Syntax: `git cat-file -p [FULL hash]`
-  `-p` means "pretty print". It's a mandated argument.
- `[FULL hash]` is just the full commit hash, no need to separate first 2 chars.

## Git Config

`git config` is self explanatory. Configure git settings.
-  Local vs global? `--local` is for just your repository whereas `--global` is repository agnostic and stored in `~/.gitconfig` file (key `~`, so root.)

`git config set user.name` sets username
`git config set user.email` sets email
`git config unset [blah blah]` unsets the keypair (removes it basically)
`git config list` lists all key pairs

`git config unset --all [blah blah]` removes ALL matches to keypair (as one key can have numerous values in Git for some reason)

## Git Branches

With git, there isn't just a singular branch. For multiple people using Git, or when fixing / testing certain features on a codebase WITHOUT altering the main one, you tend to use a _new branch_ where you fix the bug / add the feature BEFORE "merging" it to the `main` or `master` branch (whatever the default branch is).

`git branch new_branch` >> creates a new branch (assuming the branch hasn't been made yet). This DOES NOT switch to the new branch, so **DONT USE THIS**. It isn't deprecated or anything. It is just better not to.

The _better_ alternative is: `git switch -c new_branch` which creates a new branch and moves / switches into it.

On that note, there is also just `git switch new_branch` which switches into a new branch without creating one if it doesn't exist. This can also be used.

Older code may use `git checkout new_branch` for switching. It effectively does the same thing as `git switch` while remaining a bit weirder to remember and doesn't support `-c`.

`git branch` lists all current branches while highlighting the one you are currently in.

`git branch -d new_branch` deletes the branch referenced.

## Git Merging

Along with branches, upon finishing whatever you needed the branch for: (e.g: fixed the bug / implemented the change) you can merge the code into a different (usually main) branch.

`git merge new_branch` merges the referenced branch (in this case it is `new_branch`) to the current branch that you are in. This means you'd need to `git switch main` first before merging another branch to main.

See More: [[GitHub]], [[Linux Commands]]