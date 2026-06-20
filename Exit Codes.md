a.k.a: `return codes` / `status codes`

If a program is successful, it returns `0`, otherwise it'd return another number.

Use this to tell that a program ran successfully.

Use `echo $?` to see the exit code of the **last executed command**

e.g:

```bash

echo "Howdy!"
echo "$?"

# 0
```

(Definition - What is `$?` : `$?` just means the result of the last program / command ran.$)

See [[Linux]], [[Linux Commands]], [[Bash]] / [[bashrc]]