# Useful Bash CLI Commands

<br>

### Open a file from within Bash CLI on Windows

```powershell
# If there is no spaces in the file name 
start <file_to_open>

# OR

# If there is a space or more in the file name
start "" "<file_to_open>"
```

Note that the file will be opened in the default program that is set to open these type of files. More info: [t.ly/zbebX](https://t.ly/zbebX) and [t.ly/eOYOD](https://t.ly/eOYOD).

<br>

### Copy one or more files or directories to another location

```shell
# If the destination file or directory doesn't exist, it will be automatically created
# More info: t.ly/0DL1X and t.ly/8q8A0
cp -R <source_file_or_directory> <destination_file_or_directory>
```

<br>

### Remove (Delete) one or more files or directories

```shell
# More info: t.ly/3ER8w
rm -rf <file_or_directory_to_delete>
```

<br>

### Rename a file or a directory

```shell
mv -T <source_file_or_directory> <destination_file_or_directory>
```

<br>

### Move a file or a directory into a specific directory

```shell
mv <source_file_or_directory> <destination_directory>
```

<br>

### Search for a file

```shell
# List filenames ending in ".mp3", searching in the current
# folder and all subfolders. To seach in the current folder
# only, use this flag with the command "-maxdepth 1"
find . -name "*.mp3" -maxdepth 1
```

<br>

### How to empty a file without opening it (i.e. remove its content)?

```shell
# Empty a file without opening it (i.e. remove its content). 
# More info: t.ly/RMwNb and t.ly/pv2p9 and t.ly/gwJE6
# Supposing the file you want to empty is file-name.log
> file-name.log
```

