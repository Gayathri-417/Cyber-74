 
## 1) Creating directory/folder

mkdir directory_name
mkdir folder1 folder2 folder3  # Create multiple directories
mkdir -p parent/child/grandchild  # Create nested directories

## 2) Creating file inside folder 

mkdir prjct
cd prjct //you're in the prjct folder//
touch myfile.txt

## 3) Creating multiple files in folder

Method 1: Using touch with multiple filenames
touch file1.txt file2.txt file3.txt

Method 2: Using touch with curly braces (for sequential files)
touch file{1..5}.txt


## 4) Write content in the file (3 methods)

Method 1: Using Nano
nano myfile.txt
Inside nano:

Type whatever you want to write

Press Ctrl + X to exit

Press Y to save changes

Press Enter to confirm filename

Method 2: Using Echo(for single lines)

echo "Hello World" > myfile.txt

Method 3: Using cat(for multiple lines)

cat > myfile.txt
This is line 1
This is line 2
This is line 3
Press Ctrl + D when finished typing to save

## 5) To see the content  inside your file

cat myfile.txt

## 6) Delete directory/folder.

First, let's check what directories you have  ls -l

Method 1: Delete an empty directory
rmdir directory_name

Method 2: Delete a directory with contents (files and subfolders)
rm -r directory_name

Method 3: Delete directory forcefully (no confirmation)
rm -rf directory_name

Method 4: Delete directory with confirmation prompt
rm -ri directory_name

Method 5: Delete multiple directories at once
rm -r dir1 dir2 dir3

## 7) how to delete a single file in a folder:

First, navigate to your folder and see what files you have

Method 1: Delete a single file using rm
rm filename.txt

Method 2: Delete file from outside the folder
rm prjct/filename.txt

## 8) Changing/ modification of  permissions for a file.

Method 1: Using Symbolic Mode (letters)

Add permissions:

chmod u+x filename.txt  # Add execute for owner (user)
chmod g+w filename    # Add write for group
chmod o+r filename    # Add read for others
chmod a+x filename    # Add execute for all (user,group,others)

Remove permissions

chmod u-x filename    # Remove execute from owner (user)
chmod g-w filename    # Remove write from group
chmod o-r filename    # Remove read from others

Set exact permissions:

chmod u=rwx filename  # Owner can read,write,execute
chmod g=rx filename   # Group can read,execute
chmod o=r filename    # Others can only read

Method 2: Using Numeric Mode (numbers)

Common permission combinations:

chmod 777 filename    # Full access for everyone (rwxrwxrwx)
chmod 755 filename    # Owner:rwx, Group:r-x, Others:r-x (common for scripts)
chmod 700 filename    # Only owner can do everything (rwx------)
chmod 644 filename    # Owner:rw-, Group:r--, Others:r-- (common for text files)
chmod 600 filename    # Only owner can read/write (rw-------)
chmod 400 filename    # Read-only for owner (r--------)

## 9) copy a file and directory/folder to any folder/directory

Copy file to same directory (with different name)
cp file1.txt file1-backup.txt

Copy file to different directory
cp file1.txt /home/hacker/Documents/

Copy file to subfolder
cp file1.txt subfolder/

Copy multiple files to another folder
cp file1.txt file2.txt /home/hacker/Downloads/

## 10) COPY A FOLDER/DIRECTORY to another folder

Copy folder with all contents (must use -r)
cp -r prjct /home/hacker/Documents/

Copy folder to another location with different name
cp -r prjct /home/hacker/Desktop/myproject

Copy folder contents to another folder
cp -r prjct/* /home/hacker/Downloads/

## 11) CUT/MOVE A FILE to another folder

Move file to different directory
mv file1.txt /home/hacker/Documents/

Move file to subfolder
mv file2.txt subfolder/

Move and rename file simultaneously
mv file1.txt /home/hacker/Documents/newfilename.txt

Move multiple files to another folder
mv file1.txt file2.txt /home/hacker/Downloads/

## 12) CUT/MOVE A FOLDER/DIRECTORY to another folder

Move entire folder to another location
mv prjct /home/hacker/Documents/

Move and rename folder
mv prjct /home/hacker/Desktop/newproject

Move folder inside another folder
mv prjct /home/hacker/Downloads/backups/

Move folder contents to another folder
mv prjct/* /home/hacker/Documents/

## 13) SELECTING ALL FILES AT ONCE IN A FOLDER

Using * (wildcard) - selects all files
 ls *              # List all files

Copy all files to another location
cp * /home/hacker/Documents/

Move all files to another folder
 mv * /home/hacker/backup/

Delete all files
 rm *

Change permissions for all files
 chmod 644 *

Select only specific types of files
 ls *.txt          # Select all text files

 cp *.jpg /home/hacker/Pictures/   # Copy all images

 rm *.log          # Delete all log files

Select all files including hidden ones (.*)
  ls -la            # Show all files including hidden

  cp * .* /dest/    # Copy all files AND hidden files

Count all files
  ls * | wc -l      # Number of files


