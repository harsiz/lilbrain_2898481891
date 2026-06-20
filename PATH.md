PATH is a way to not need to call the absolute path when trying to execute something in [[Linux]].

```bash
export PATH="$PATH:/path/to/file"
```

That let's you call the file directly to execute it.

e.g: let's say the file was `good.sh` in the `good_sh_dir` directory.

```bash
export PATH="$PATH:/home/my_file/good_sh_dir"
```

See: [[Bash]], [[bashrc]], [[Linux Commands]]