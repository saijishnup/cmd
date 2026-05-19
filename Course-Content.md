# Command Prompt Course - CODEDEX

## PART A: Navigation
> __NOTE:__ `$` sign is just for representation, while typing it is not required 

<hr style="border:2px dashed black">

### Chapter 1: echo
> **In CMD**, `echo` is used for displaying text (like printf).
- In Git Bash, type:
```sh
$ echo Hi! My name is Jishnu
```
- It prints: `Hi! My name is Jishnu`

---
### Chapter 2: pwd
- A computer is a filesystem made of folders and files.
- In the context of CMD, folders are called **directories**.

> **PWD (Present Working Directory):** Shows your current location in the filesystem.
```sh
$ pwd
```
- It prints: `/c/Users/HPNEW BOOK`
---
### Chapter 3: cd, ls
> **Change Directory (cd):** Navigate from one directory to its subdirectories.
- Considering current directory: `/c/Users/HPNEW BOOK`
```sh
$ cd Desktop
```
- It navigates to the Desktop directory.
- Type `pwd` command to verify.
- It outputs: `/c/Users/HPNEW BOOK/Desktop`
- If you want to go back to `/c/Users/HPNEW BOOK`, type:
```sh
$ cd ..
```
- For multiple subdirectories:
```sh
$ cd ../..
```
- **Note:** If that subdirectory doesn't exist, it prints: `No such file or directory` 


> **List Content (ls):** Lists all subdirectories and files in the current directory.
- Considering current directory: `/c/Users/HPNEW BOOK`
- If we type:
```sh 
$ ls
```
- It will list out all the subdirectories and files present in it. Example:
```
Desktop
Documents
Images
notes.txt
```
- Items without extensions are subdirectories.
- Items with extensions are files in that directory.
---
### Chapter 4: cat
> **Viewing File Content with cat:** Prints all text-based content from a file to the command line.
- Considering current directory: `/c/Users/HPNEW BOOK`
- After `ls`, if you want to open `notes.txt`, type: 
```sh
$ cat notes.txt
```
- **Note:** The `echo` command can also be used for viewing file content, but `cat` is more commonly used.

---
### Chapter 5: clear, tab, `↑` and `↓`
> **clear:** Clears everything from view on the command line.

> **Command History:** By using `↑` and `↓` arrow keys, you can navigate your previous commands.

> **tab:** Auto-completes the filename or command. If multiple files match, it displays all matching names for what you've typed.

---
### Chapter 6: Scavenger Hunt
> This chapter takes you through a fun technical game using CMD.

[Click here](https://www.codedex.io/command-line/06-scavenger-hunt) for instructions!  
P.S.: The reward is worth playing for.

<hr style="border:2px SOLID black">

## PART B: Manipulation
There is more beyond what you imagine...  
Here the REAL GAME starts!

<hr style="border:2px dashed black">

### Chapter 7: mkdir
> **Make Directory (mkdir):** Short for "make directory". Creates a new directory inside the current directory.

- **Note:** `mkdir` doesn't move you into the newly created directory.

- Make a new directory called:
```sh
mkdir recipe
```
- Check using `ls` if it was created.

---
### Chapter 8: touch
> **Create New File (touch)**

- You can create files with all kinds of extensions like `.txt`, `.py`, etc. using the `touch` command.
- It looks like:
```sh
touch mac-n-cheese.txt
```
- You can even create new files in an existing subdirectory:
```sh
touch favourite-dish/mac-n-cheese.txt
```
- **Note:** Make sure the subdirectory `favourite-dish` is already created in the `recipe` directory using the `mkdir` command.

---

### Chapter 9: echo - Writing to a File
> **Write to a File using echo**

```sh
$ (
> echo Ingredients:
> echo - Macaroni
> echo - cheese
> echo - salt and pepper
> echo - mixed herbs
> ) > ingredients.txt
```

- Here `>` overwrites any existing content in a file.
- But `>>` appends content to a file without changing what already exists.
```sh
$ ( echo - butter and oil ) >> ingredients.txt
```
- You can see the changes using the `cat` command.
- If you want text on a new line, use the `;` symbol wherever the existing line ends.
- **Note:** If the file doesn't exist, it will be created automatically!

> **Combine Files:** Combine the text of two files.

Here `cat` is also used to put content from one file into another:
```sh
$ cat ingredients.txt instructions.txt > mac-n-cheese.txt
```
- This will write the contents of both files into `mac-n-cheese.txt` (override).
- If you want to append instead of overwrite:
```sh
cat file-b file-c >> file-a
```
---
### Chapter 10: mv, rm, rmdir, -r

> **Move Directories & Files Using `mv`:** You can move a file or directory from one place to another.

```sh
$ mv file-a folder-b/
```
- Specify the file or directory you want to move, followed by the directory where you want to move it.
- Use `/` to be more specific about the destination.
- **Note:** If you're moving a directory, everything inside it will be moved as well.

> **Rename Using `mv`:** You can use the `mv` command to rename existing files and directories:

```sh
$ mv folder-a folder-b
```
- If the second argument of `mv` is neither a file nor a directory, the first argument is renamed to that. 
- This renames the `folder-a` directory to `folder-b`.

> **Remove Directories & Files Using `rm`**

**For files:** Use the `rm` command (short for "remove").
- You can remove a single file:
```sh
$ rm file-a
```
- Or remove multiple files in a single command:
```sh
$ rm file-a file-b file-c
```
**For removing directories:** Use the `rmdir` command.
- You can remove a single directory:
```sh
$ rmdir folder-a/
```
- Or remove multiple directories (each separated by space):
```sh
$ rmdir folder-a/ folder-b/ folder-c/
```
- **Note:** The `rmdir` command only removes empty directories.
- If there's anything inside a directory, this command will not work.

To remove a non-empty directory, use the `rm` command with a special `-r` flag:
```sh
$ rm -r folder-a
```
- This will remove the `folder-a` directory along with everything inside it.

- The `-r` flag deletes content recursively, meaning it deletes even hidden files and subdirectories.

**Note:** To prevent unexpected behavior, make sure to change out of a directory before removing it with `rm`. This means:

- If you are currently inside a directory, deleting that same directory can cause errors because the terminal is using it.
```sh
$ cd ..
$ rm -r folder-a
```

---

### Chapter 11: cp, cp -r
> **Copy Files Using `cp`**

**For copying file content** to another file, use the `cp` command (short for "copy"):

```sh
cp file-a file-b
```
This will make a copy of `file-a` and copy its contents to `file-b`.

- If `file-b` does not exist, it is created automatically.
- If it does exist, all contents are overwritten with what is copied from file-a.

> **Copy Directories Using `cp -r`**

```sh
cp -r directory-a/ directory-b/
```
You must include the `-r` (recursive) flag to copy everything from one directory to another.

- Just like with files, `directory-b` is automatically created if it doesn't yet exist.
- Otherwise, its content is overwritten with what is copied from `directory-a`.

To create a copy of a directory:
```sh
$ cp -r directory-a directory-copy
```
All files and subdirectories in `directory-a` are copied to `directory-copy`.

---

### Chapter 12: Music Playlist

This is a game/task. I haven't completed this yet. If you want to try it:
[Click here](https://www.codedex.io/command-line/12-music-playlists)

<hr style="border:2px SOLID black">

 **The End!**  
Started: 19-05-2026 (afternoon)  
Ended: 19-05-2026 (midnight)