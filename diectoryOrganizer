import os
import shutil

# This defines the file categories and corresponding folders
cats = {
    'Images': ['jpg', 'jpeg', 'png', 'gif'],
    'Videos': ['mp4', 'avi', 'mov', 'mkv'],
    'Documents': ['pdf', 'doc', 'docx', 'txt'],
    'Others': []  # This is for outliers or files with unknown or unsupported extensions
}

# This prompts the user to enter the path to the directory to be organized (target)
tar_dir = input("Enter the path for the directory you want to organize:")

# This creates folders for each category if they don't exist
for cat in cats:
    folderPath = os.path.join(tar_dir, cat)
    if not os.path.exists(folderPath):
        os.makedirs(folderPath)

# This scans the target directory and organize files
for fileName in os.listdir(tar_dir):
    filePath = os.path.join(tar_dir, fileName)
    if os.path.isfile(filePath):
        _, ext = os.path.splitext(fileName)
        ext = ext.lower()[1:]  # This removes the dot from the extension
        for cat, exts in cats.items():
            if ext in exts:
                dest_folder = os.path.join(tar_dir, cat)
                shutil.move(filePath, os.path.join(dest_folder, fileName))
                break
        else:
            dest_folder = os.path.join(tar_dir, 'Others')
            shutil.move(filePath, os.path.join(dest_folder, fileName))
