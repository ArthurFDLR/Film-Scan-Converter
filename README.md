# Film Scan Converter
A python GUI used for processing RAW film scans from a digital camera into final images

# Installation
If you do not have Python installed, you can simply download and run the Windows executable below:  
[Download Link](https://www.dropbox.com/scl/fi/zq8qo2jtjipaxj235cg45/Film-Scan-Converter.exe?rlkey=qa9fkiy7h1svsi9ixnrz83pg5&e=2&st=43ddm53m&dl=0)

If you want to run it on a different platform (e.g. MacOS) or you have security concerns around running a random EXE you downloaded from the internet, you will need to install Python 3.10 or newer, download the source files, install the dependant libraries, and run the "Film Scan Converter.pyw" file with Python.

# Overview of Features
## Batch Processing
This program enables you to import multiple RAW scans (most RAW image formats supported), and process them all simultaneously. Each photo's settings can either be synced with global settings, or have settings independent from all the other photos. This is useful when all the photos are scanned in a consistent manner, or you want to dial in the same "look" for multiple photos.

A potential workflow is as follows:
1. Import RAW scans from the same batch and film stock. By default, all photos are synced with global settings.
2. Set the film type (i.e. B&W, Colour, Slide).
3. Set the dark and light threshold so that most photos are cropped properly.
4. If the entire roll has been scanned on the reverse side, the image can be flipped.
5. If applicable, set the colour of the film base.
6. Go through each photo to check that it has been cropped/inverted properly. You can use the arrow keys to cycle through each photo.
7. If an individual photo needs adjustment, uncheck "Sync with Global Settings", then apply the adjustment.
8. Click "Export All Photos".

## Automatic Cropping
By setting the appropriate dark and light threshold values, the program can automatically find the optimal crop around a photo. For best results, ensure the following during scanning:
1. Use a film holder to hold the film flat and undistorted during scanning.
2. Use a reasonably accurate mask around the photo. Some film holders have notches or cutouts around the film frame; masking tape can be used to cover up the notches and square off the edges.
3. Fill the image frame as much as possible with the desired photo.
4. Use a consistent exposure and orientation across the entire roll of film.

An ideal film scan is shown below:  
![image](https://github.com/user-attachments/assets/7aa530f8-f0b6-4345-bfed-0cb2fa739b9c)

The dark and light threshold values define the minimum and maximum brightness levels of the region of the RAW scan containing the desired photo. An appropriately thresholded image highlights most if not the entirety of the desired image, and excludes the mask and/or the film base. In the "Threshold" view, it should look like a white box surrounded by a black border, as shown below:  
![image](https://github.com/user-attachments/assets/4a768370-e47c-48a8-b76f-8cd934c5d924)

You can verify that the program has detected the photo properly using the "Contours" view. The final crop of the photo is shown as a green rectangle, as shown below.  
![image](https://github.com/user-attachments/assets/fd3e44ec-31f6-4054-8ad6-28ee4ad2ae37)

If the mask has fuzzy edges, this may show up near the borders of the final image. You can either increase the Border Crop, or fine tune the light and dark threshold values to try crop it out.
