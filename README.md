# Baidu Street View Spider


This project is used to get the street view image of Baidu map at the corresponding location based on the specified wgs84 latitude and longitude coordinates.


## Contents


This folder mainly contains a script file for getting street view and an output directory.


+ baiduStreetViewSpider.py: this script is the main program to get the street view, the input is a csv file with the latitude and longitude information in wgs84 coordinate system.


+ dir folder: the input files of the script and the output street view images and crawl failure information. This folder contains mainly the following files:
  1. point_coordinate_50, point_coordinate_100 and point_coordinate_intersect are the latitude and longitude information of the missing 50m encrypted points, 100m encrypted points and road intersections of the road network respectively.
  2. the error file is the information of the corresponding failed points.
  3. images folder will save the images of successfully crawled street view.


## Environment dependency


　　The script runs in python3 environment, and needs to import re, os, json, requests, time, glob, csv, traceback libraries, among which all are built-in python modules except requests library which is a third-party library, no additional installation is needed.


　　Regarding the requests library, the version is 2.26.0, and the installation method is


``` python
  pip install requests
```


## Tips


1. Using arcgis or QGIS to extract the latitude and longitude information of street view data, and store it in csv file. 2.
2. line 102 contains the read_fn variable, which is the name of the csv file with the latitude and longitude information.  
3. error_fn variable (line 103) is the filename of the csv file with the latitude and longitude information.
4. line 105 of the code wgs_x and wgs_y are the list of latitude and longitude respectively, where the second dimension of the data variable represents the column index of the latitude and longitude in the csv file.
5. If the error is reported as no response from the connected host, you need to extend the sleep time in line 158 to a multiple of 3 appropriately.
6. the street view file is named as follows: longitude latitude angle pitch angle, if the crawl is successful, each point will crawl 0 degree, 90 degree, 180 degree and 270 degree street view.
7. wgs84 coordinates will be automatically converted to Baidu's coordinates in the program using the wgs2bd09mc function, no additional operation is needed.


## References
[1] Yao, Y., Liang, Z., Yuan, Z., Liu, P., Bie, Y., Zhang, J., ... & Guan, Q. (2019). A human-machine adversarial scoring framework for urban perception assessment using street-view images. International Journal of Geographical Information Science, 33(12), 2363-2384.


[2] Helbich, M., Yao, Y., Liu, Y., Zhang, J., Liu, P., & Wang, R. (2019). Using deep learning to examine street view green and blue spaces and their associations with geriatric depression in Beijing, China. Environment international, 126, 107-117.


[3] Yao, Y., Wang, J., Hong, Y., Qian, C., Guan, Q., Liang, X., ... & Zhang, J. (2021). Discovering the homogeneous geographic domain of human perceptions from street view images. Landscape and Urban Planning, 212, 104125.


[4] Yao, Y., Zhang, J., Qian, C., Wang, Y., Ren, S., Yuan, Z., & Guan, Q. (2021). Delineating urban job-housing patterns at a parcel scale with street view imagery. International Journal of Geographical Information Science, 35(10), 1927-1950.




## Declaration
This code is for scientific use only, please do not use it for any non-scientific or illegal purposes.


Thanks to Dr Yao Yao (yaoy@cug.edu.cn) for the learning materials, I modified these according to his code.
