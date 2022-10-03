# Linux Terminal
Here are terminals commands that I've mastered and can use in my work.

The document is built on the principle of task - answer.

### Work with files and file system:

1. Using `echo` with the necessary key, output the text “Script1 Script2 Script3” to the console in three lines.
```sh
echo -e "Script1\nScript2\nScript3"
```

2. Output all options for `ls`.
```sh
ls --help
```
or
```sh
man ls
```

3. Create a folder in your home directory. Create a file file1.txt in it with the text "123abc". Output the contents of the created file to the console.
```sh
mkdir folder1 &&  echo "123abc" > folder1/file1.txt && cat folder1/file1.txt
```

4. Using `mkdir` with a certain option, create the folder ./folder1/folder2/folder3 in the home directory (at the time of creation, folder1 should not have folder2 in it).
```sh
mkdir -p folder1/folder2/folder3
```

5. Copy file1.txt to home directory with a new name.
```sh
cp folder1/file1.txt ~/new_file1.txt
```

6. Copy file1.txt to folder3.
```sh
cp folder1/file1.txt folder1/folder2/folder3
```

7. Create a move folder. Move folder1 with all contents to the move folder.
```sh
mkdir move && mv folder1 move
```

8. Copy all the contents of the move folder to the copy folder, having previously created it.
```sh
mkdir copy && cp -R move copy
```

9. Create file1.txt in your home directory. Change its last modified date.
```sh
touch -t 2208311000 ~/file1.txt
```

10. Delete the copy folder with all its contents.
```sh
rm -r copy
```

11. Go to ~/move/folder1/folder2/folder3 folder. Output the full path of a directory to the console.
```sh
cd ~/move/folder1/folder2/folder3 && pwd
```

12. Find the file(s) in the /etc directory that contain the word "release" in their name.
```sh
find /etc -type f -name "*release*"
```

### Work with users, groups and file permissions:

1. Create a new user lastname-user1.
```sh
sudo useradd panfilova-user1
```

2. Set him a new password.
```sh
sudo usermod -p 123456 panfilova-user1
```

3. Create a group lastname-group1.
```sh
sudo groupadd panfilova-group1
```

4. Set lastname-group1 as primary for lastname-user1.
```sh
sudo usermod -g panfilova-group1 panfilova-user1
```

5. Add the ability to use `sudo` for the user lastname-user1.
```sh
sudo usermod -a -G sudo panfilova-user1
```

6. Create an empty file lastname-homework and view its permissions.
```sh
touch panfilova-homework && ls -l
```

7. Set permissions for file lastname-homework: owner - all rights, group - read, others - read and execute.
```sh
sudo chmod 745 panfilova-homework
```

8. Change the owner of the file lastname-homework to lastname-user1.
```sh
sudo chown panfilova-user1 panfilova-homework
```

### Working with the APT:

1. Add repository *ppa:alexx2000/doublecmd*.
```sh
sudo add-apt-repository ppa:alexx2000/doublecmd
```

2. Get information about *doublecmd* from repositories.
```sh
sudo apt-get update
```

3. Install *doublecmd* and *nginx* with `apt-get`.
```sh
sudo apt-get install doublecmd
sudo apt-get install ngnix
```

4. Get information about all packages installed on the system.
```sh
apt list --installed
```

5. Remove *doublecmd*.
```sh
sudo apt-get remove doublecmd
```

6. Delete *doublecmd* configuration files.
```sh
sudo apt-get purge doublecmd
```
