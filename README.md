# Advanced_Lane_Finding_P4
Lane finding using more advanced algorithms.
Much more complex version of Project 1.

The code starts in the second cell. It uses three functions to filter the input images.  These functions use the Sobel, Magnitude, and Direction gradients to identify lines in the original images. These three processes are combined in the fourth function to generate the thresholded Gradient image below. It is the basis for identifying lane lines in subsequent images. 

A color threshhold function is included, but not used. My tests show it did not improve the final results.

A camera calibration step corrects for distortions in the camera lens. This takes in a standard "chess board" image to measure the distortion of the lens, then subsequent images are corrected based on the chess board output. Notice the orignial image of the curved highway sign. Then look at it's corrected straight image at the end of the calibration section.

Next a perspective transform gives a simulated overhead image of the road. It's much easier to judge lines from above.

The Line Object cell defines the line parameters.

Finding Lane Curvature. Half of this code is commented out used only for testing. The other half is math to recognize and quantify lines in images. project_lines highlights the lane lines in the output image.

Processing Image Code calls the above functions. The image in the first line 'camera_cal/calibration*.jpg' if for calibrating the camera. The line, 
   
   image = mping.imread('test_images\Btest2.jpg') is the input image.
   
Video Pipeline does the same thing on input video. Processing Video calls the viedo pipeline on 'project_video.mp4' and produces 'test.mp4' as output.

Look at the 'challenging.mp4' video to see some of the shortfalls of this program. Paving lines and old lane lines confuse it. Sometimes I can not tell where the lines are supposed to be after the lanes have been moved 4 or 5 times after constuction and the old lines have not been removed.












