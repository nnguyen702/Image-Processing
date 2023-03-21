# Image-Processing7.2 Image Processing

Ngoc Nguyen is responsible for this module.
7.2.1 Processing narrative for Image processing
	In this module, its job is to take the image of the area where the whiteboard presents.
  Only the estimated size of the whiteboard gets into the detection; 
  the biggest object in the image (which should be the whiteboard). 
  In the detection, it checks the area on the whiteboard where the marks are.

7.2.2 Image processing interface description 
The image processing starts when receiving a control signal from the user interface via the input button. 
This action is to tell the matlab to take a picture of the whiteboard by webcam (connect to raspberry pi). 
After running through the algorithm inside matlab on PC, the array of sections (area on whiteboard go by integer number) 
are the outputs. The Arduino Mega receives these output arrays from matlab via BT communication. 

7.2.3 Image process processing details
	Pushing the button is to start the process.
  Matlab receives a signal from the button, then calls the function to get a snapshot from the webcam (on raspberry pi).
  Matlab runs the function read() to get access to the taken picture by raspberry pi. 
  The picture runs into the algorithm for detection. 
  In the detection process, it crops the area of the actual whiteboard in the image and converts it to grayscale image. 
  Then, it divides the cropped image into a number of sections ( which is 12 in the code).
  These twelves sections will go through the checking pixels. 
  This task checks each of the sections if they contain any of black pixels. 
  By calling the blackpixel() function for each section, if it is true, this section’s number is added to output arrays.
