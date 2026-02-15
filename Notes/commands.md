 
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

## 7) First, navigate to your folder and see what files you have

Method 1: Delete a single file using rm
rm filename.txt

Method 2: Delete file from outside the folder
rm prjct/filename.txt


