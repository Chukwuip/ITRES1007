# Problem 5
See the problem_5 subdirectory.
A client wishes to put information on our Omniglobe (https://arcscience.com/omniglobe-technology/).
They provided a series of NetCDF files with names like: ozone_8dec2009.nc, ozone_7dec2009.nc, 
ozone_9dec2009.nc, ... etc.
A python script is used to access the files, extract some data and produce 2D images in PNG format.
The software for the Omniglobe:
• scans the contents of a folder
• generates an animated sequence from the PNG files contained in the directory.
This fragment of the Python script sets up the filenames to be written.   



````
#Build up filename
VarName = "Ozone_"
TimeStamp = "2001-01-01" # this could be in the nc file
Frame = str("%04d"%simhour)
MetaData = VarName+TimeStamp+"_"+Frame
fname_out = Home+MetaData+".png"
# create the file
savefig(fname_out, bbox_inches="tight", pad_inches=0.0)
````
In the script fragment above:  
(i) Can you determine the content of the fname_out variable?  
(ii) What information is missing?


# Solution

**(i) Content of fname_out variable:**  
The fname_out variable is constructed by concatenating the following strings: Home, MetaData and .png  

Home: Is not defined elsewhere in the script, although it seems to represents the path to the directory where the PNG file is saved.
MetaData: This variable combines the following varables, VarName, TimeStamp, and Frame. It creates a unique identifier for each PNG file.
".png": is the file extension indicating that the file will be in PNG  photo format.
Therew the content of fname_out is the full path to the PNG file that will be created.

**(ii) Missing information:**  
The following information is missing and or are not fully explained in the script provided:

**The value of the Home variable:** The script assumes that Home is a variable representing the path to the directory where the PNG files will be saved. The actual value of this variable is not provided in the script.

**The source of the simhour variable:** The script uses simhour in constructing the Frame variable, but the source or calculation of simhour is not shown in the provided fragment.

**The origin of the TimeStamp variable:** The comment suggests that this information could be in the NetCDF file, but the script fragment does not show how TimeStamp is obtained from the NetCDF file.
To use this script in a real-world scenario, you would need to make sure that these missing pieces are defined or calculated correctly. Additionally, it's essential to ensure that the NetCDF files contain the necessary information for the script to function correctly, especially for extracting the TimeStamp.
