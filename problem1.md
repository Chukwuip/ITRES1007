**Problem 1:**  
See the problem_1 subdirectory.
A researcher has inadvertently renamed all their 100 data files with the wrong file extension and doesn’t 
know how to change them back.
Show you can rename the files to have a .dat file extension and explain to the researcher how they can 
do this themselves if they make this mistake again.


__Answers__

How I will rename the 100 files with the wrong file extentions and explain to the researchers how to do this themselves.  

I'll use a python script in the code snippe below
`````
import os

def rename_files(folder_path, new_extension=".dat"):
    """
    Rename files in the specified folder with a new file extension.
    
    Parameters:
    - folder_path (str): The path to the folder containing the files.
    - new_extension (str): The new file extension to be used.
    """
    # List all files in the specified folder
    files = os.listdir(folder_path)

    # Iterate through each file
    for file_name in files:
        # Check if it's a file (not a directory)
        if os.path.isfile(os.path.join(folder_path, file_name)):
            # Split the file name and extension
            base_name, _ = os.path.splitext(file_name)

            # Rename the file with the new extension
            new_file_name = base_name + new_extension
            os.rename(os.path.join(folder_path, file_name), os.path.join(folder_path, new_file_name))
            print(f"Renamed: {file_name} to {new_file_name}")

# Example
folder_path = 'C:/Users/<myUsername>/Documents/Python_Scripts/rseprac-master/problem_1/'  
rename_files(folder_path)

`````

I will let the researcher know that they can do these themselves in the future using the above Jupyter Notebook

- Open a new code cell in the Jupyter Notebook.
- Copy and paste the code above.
- Replace the folder_path variable with the actual path to their data files.
- They can also modify the new_extension argument if they want a different file extension.
 - Run the code cell.

The code with the run example is included below.
