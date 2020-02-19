# Useful Bash CLI Commands

<br>

### How to open a file from within Bash CLI on Windows?

```powershell
# If there is no spaces in the file name 
start /path/to/file-name.txt

# OR

# If there is a space or more in the  file name
start "" "/path/to/file name.txt"
```

Note that the file will be opened in the default program that is set to open these type of files. More info: [t.ly/zbebX](https://t.ly/zbebX) and [t.ly/eOYOD](https://t.ly/eOYOD).

<br>

### How to copy a file or a directory and its contents?

```shell
# Copy a file or a directory and all its contents
# If the destination file or directory doesn't exist, it will be automatically created
# More info: t.ly/0DL1X and t.ly/8q8A0
cp -R path/to/source/file/or/directory/ path/to/destination/file/or/directory/
```

<br>

### How to remove/delete a file or a directory and its contents?

```shell
# Remove/Delete a file or a directory and its contents
# More info: t.ly/3ER8w
rm -rf path/to/the/file/or/directory/to/delete/
```

<br>

### How to empty a file without opening it (i.e. remove its content)?

```shell
# Empty a file without opening it (i.e. remove its content). 
# More info: t.ly/RMwNb and t.ly/pv2p9 and t.ly/gwJE6
# Supposing the file you want to empty is file-name.log
> file-name.log
```

