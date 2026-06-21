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



See More: [[GitHub]], [[Linux Commands]]