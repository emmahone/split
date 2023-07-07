# The `split` command
In bash, you can split a large file into multiple smaller files using the `split` command. The `split` command allows you to specify the desired size or number of lines for each split file. After running the split command, you will have multiple smaller files based on your specified criteria. You can adjust the options of the split command according to your needs. Use the man split command in your terminal to see the full documentation and more options available for the split command.

# Splitting by file size
```bash
$ split -b 1M largefile.txt splitfile
```
This command splits the file "largefile.txt" into smaller files with a maximum size of 1MB each. The resulting split files will be named "splitfileaa", "splitfileab", "splitfileac", and so on.

# Splitting by number of lines
```bash
$ split -l 1000 largefile.txt splitfile
```
This command splits the file "largefile.txt" into smaller files with a maximum of 1000 lines each. The resulting split files will be named "splitfileaa", "splitfileab", "splitfileac", and so on.

# Customizing the output file names
```bash
$ split -b 1M largefile.txt mysplitfiles/prefix-
```
This command splits the file "largefile.txt" into smaller files with a maximum size of 1MB each. The resulting split files will be stored in the "mysplitfiles" directory with filenames starting with "prefix-".

# Joining the split files back together
To join the split files back together into a single file in bash, you can use the `cat` command. The `cat` command is typically used to concatenate and display the contents of files. However, it can also be used to combine split files.

Assuming you have split files with names like "splitfileaa", "splitfileab", "splitfileac", and so on, you can use the following command to join them back together:
```bash
$ cat splitfile* > largefile.txt
```
This command uses the wildcard `*` to match all files with names starting with "splitfile" and concatenates them together into a single file named "largefile.txt".

Make sure you run this command in the directory where the split files are located. If the split files are in a different directory, you need to provide the full path to the split files or navigate to that directory before running the `cat` command.

After running this command, you will have a single file named "largefile.txt" that contains the combined contents of all the split files.
