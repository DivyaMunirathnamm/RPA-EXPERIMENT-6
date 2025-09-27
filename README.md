# RPA-EXPERIMENT-6
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
<img width="670" height="612" alt="image" src="https://github.com/user-attachments/assets/778687f8-b169-4949-a9bc-027d29fe8532" />

<img width="695" height="647" alt="image" src="https://github.com/user-attachments/assets/f845a15b-134a-444a-a78b-aecd20e0d644" />

# OUTPUT:
<img width="919" height="154" alt="image" src="https://github.com/user-attachments/assets/959476d7-8be7-4066-b65e-980ae332b00f" />

<img width="819" height="172" alt="image" src="https://github.com/user-attachments/assets/db421231-8224-46f7-b3ec-c1bae669b6ab" />

RESULT:
The UiPath workflow successfully reads all files from a source folder, appends a timestamp to each file name, and copies them to a new destination folder.
