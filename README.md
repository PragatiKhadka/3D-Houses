### Description  
The project is based on the understanding and using the geospatial data.   
Given an address, the objective of the project is to 3D plot of any houses/buildings in that address.  
According to [Flemish government](https://overheid.vlaanderen.be/dhm-digitaal-hoogtemodel-vlaanderen-ii), the areas are divided into 43 zones. However, I was working on only 11 zones namely 1,2,3,4,5,6,7,8,9,15 and 16.

### Installation  
The libraries on the `requirements.txt` should be installed in order to run the program.  
Generally `pip install requirements.txt` is used for installation. But, in this case since I have installed some libraries using binary files it will not work. So, the installations has to be done manually for such libraries.


### Usage  
In order to run the program, follow these steps:  
1. Download the repository.  
2. Install the libraries in `requirement.txt`.  
3. Create a folder with name `data` and create two folders `DSM`and `DTM` inside `data` directory.  
4. Download the zip files from - [DSM](http://www.geopunt.be/download?container=dhm-vlaanderen-ii-dsm-raster-1m&title=Digitaal%20Hoogtemodel%20Vlaanderen%20II,%20DSM,%20raster,%201m) link and save it in folder `DSM`.  
5. Download the zip files from - [DTM](http://www.geopunt.be/download?container=dhm-vlaanderen-ii-dtm-raster-1m&title=Digitaal%20Hoogtemodel%20Vlaanderen%20II,%20DTM,%20raster,%201m) and save it in folder `DTM`.  
6. open the file `3D-house` in the jupyter notebook.  
7. run all cells in the jupyter notebook.  
8. As asked by the program, enter the input for the streetname, house number, postcode and city.  
9. It will produce a 3D plot of the object in the address if available. Otherwise a proper message will be given. It will also provide the message on which zone the polygon lies.

### Output  
Here are two sample pictures of the 3D plot of the building where BeCode is located.  
![plot1](/images/becode1.png)  
![plot2](/images/becode2.png)  

### Program flow  
1. Request the user to input the address
2. Using the address, request the api to get the coordinates of the polygon in that address, if any. If not provide a message.
3. Find in which zone the address lies using the shape files.
4. Clip the dsm and dtm tif files with respect to the matching zone.
5. calculate the canopy height model(chm) from the clipped dsm and dtm files.
6. 3D plot the chm using plotly.  

### Technical Difficulties  
1. Installation of the required library such as gdal, rasterio and fiona was a challenge on a windows operating system. Finally, I had to install these libraries using the binary files.
2. At the beginning, figuring out the flow of the program was difficult. It was confusing what to do, how to do and check whatever I was doing was on a right path. 