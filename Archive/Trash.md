# Trash

## Trashed file location
(from [stackoverflow](https://askubuntu.com/a/877594/877408)) The trashed files will be put on:

- Deleted files on your "home" partition go to: `/home/username/.local/share/Trash`
- Deleted files on other partitions go to `/.Trash-$UID`, without rw access to that folder, no trash.

## Commands
From glib2 package (gnome official package):

- `gio trash [FILE1] [FILE2] ...` to trash files
- `gio trash --empty` to empty the trash

From trash-cli package (third party package on [Github](https://github.com/andreafrancia/trash-cli)):

```
trash-put FILE1           trash files and directories.
trash-list | grep FILE1   list trashed files.
trash-restore FILE1       restore a trashed file.
trash-empty 30            remove files older than 30 days.
trash-empty               empty the trashcan(s).
trash-rm FILE1            remove individual files from the trashcan.
trash-rm \*.txt           remove individual .txt files.
```

Alias in *.zshrc*:

- `trash-ls` print trashed files that were in the current directory, sorted by date

## Delete on scheduling
`0 0 * * * trash-empty 30` crontab set to check every at midnight every day to delete files older than 30 days.