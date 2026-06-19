
[[Backend]], [[Unix]]

## Permissions
Look like:

`-rwxrwxrwx`
(read, write execute)
(owner is first rwx, group - ignore this, others)
("-" means normal file)
("d" means directory)

### Change Permissions

use **chmod** (or "change mode") to do this.

u= user (owner)
g= group
o= others

leaving them empty just sets to nothing.

e.g:

`chmod u=rwx,g=,o= DIRECTORY_PATH`