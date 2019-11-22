# GetGrainSize
[Material Science] Measure grain size based on the Heyn intercept method.

![sample](https://github.com/kyphd/GetGrainSize/blob/master/output/000.png)

# About
This program is to measure the grain size based on the Heyn intercept method [E. Heyn, The Metallographist, Vol. 5, 1903, pp. 39-64.]. A monochrome image file is required and grain boundary is described with black line. If you want, some images are randomly cropped, and measure the grain size for each cropped image.

# Requre
## python 3

https://www.python.org/

## module
numpy, pillow are required.
```
pip install numpy pillow
```

## Image file

You need to prepare the monochrome image file in which grain boundaries are shown with black line.

# Execute

```
python getgrainsize.py -f <filename> -c -s <width> <height> -n <number>
```

Each option is separated by space. 

## options

-f \<filename\> : Image filename. \[mandatory\]

-c : Crop mode. Some images are croped from image file randomely, and measure the grain size for each cropped file. \[optional\]

-s \<width\> \<height\> : Width and height of cropped image. \[mandatory for crop mode (-c)\]

-n \<number\> : Number of crop images. \[mandatory for crop mode (-c)\]

## example 1

To measure the grain size in sample.tif, run getgrainsize.py as follows.

```
python getgrainsize.py -f sample.tif
```

## example 2

If you want 3 crop images (width and height is (200, 200)) from sample.tif, and want to measure each grain size, run as follows.

```
python getgrainsize.py -f sample.tif -c -s 200 200 -n 3
```

# output

"output" directory is made and result files are saved.

result.dat : Results are saved in this file. The same as STDOUT. D_x is the average grain size measured by line no.x (x = 0, 1, 2,...). D_ave is the average grain size from the image.

\<filename\> : The copy of the original image file. Lines and interceptions are shown. As for the crop mode, the cropped areas are shown in this file.

000.tif, 001.tif, ... : For the crop mode, cropped images are generaged. Lines and interceptions are shown.


# Authors

* **K. Yabuuchi** 
* See also the list of [contributors](https://github.com/kyphd/GetGrainSize/contributors) who participated in this project.

# License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details