# RPA-EXPERIMENT-6
# NAME : DIVYA M
# REG NO: 212223040043

# AIM:
To create a UiPath workflow that copies all files from a source folder to a destination folder and renames them by appending a timestamp to each file name.

# ALGORITHM:
Step 1: Create a New Process Open UiPath Studio and create a new process named CopyRenameFiles.

Step 2: Create Input Variables Create the following variables in the Variables panel:

Name : Type Default Value (optional) sourceFolder : String "C:\Users\YourName\Documents\SourceFiles" destFolder : String "C:\Users\YourName\Documents\RenamedFiles" files : String[] (leave blank)
Step 3 : Get All Files from Source Folder Drag an Assign activity: files = Directory.GetFiles(sourceFolder)

Step 4: Use For Each to Loop Through Files i. Add a For Each activity. ii. ForEach item: file In files iii. Set TypeArgument to String.

Step 5: Inside the Loop – Generate Timestamp Add an Assign activity inside the loop:

timeStamp = Now.ToString("yyyyMMdd_HHmmss")
Create a timeStamp variable of type String.
Step 6: Get File Name and Extension

Add two Assign activities: fileName = Path.GetFileNameWithoutExtension(file) extension = Path.GetExtension(file) (Create fileName and extension variables of type String)
Step 7: Build New File Name Add Assign:

newFileName = fileName + "_" + timeStamp + extension (Create newFileName as a String variable)
Step 8: Copy File to Destination Folder

Add another Assign: destPath = Path.Combine(destFolder, newFileName) (Create destPath as a String variable)
Then use Copy File activity: From: file To: destPath
# PROGRAM:

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1e529afd-abee-4cc6-8c90-ea09a2c540f1" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/dce817d8-287c-4f24-bb4e-416c909cd0c5" />


# OUTPUT:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4d40cd12-fa83-4f69-91c0-13970028de04" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8ca7f273-16c1-4f06-8f9b-a9f314efba97" />

RESULT:
The UiPath workflow successfully reads all files from a source folder, appends a timestamp to each file name, and copies them to a new destination folder.
