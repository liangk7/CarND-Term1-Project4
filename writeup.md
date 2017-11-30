# **Advanced Lane Finding**

---

**Advanced Lane Finding Project**

The goals / steps of this project are the following:

* Compute the camera calibration matrix and distortion coefficients given a set of chessboard images.
* Apply a distortion correction to raw images.
* Use color transforms, gradients, etc., to create a thresholded binary image.
* Apply a perspective transform to rectify binary image ("birds-eye view").
* Detect lane pixels and fit to find the lane boundary.
* Determine the curvature of the lane and vehicle position with respect to center.
* Warp the detected lane boundaries back onto the original image.
* Output visual display of the lane boundaries and numerical estimation of lane curvature and vehicle position.

[//]: # (Image References)

[image1]: ./output_images/fig_cameraCal.png "Camera Calibration"
[image2]: ./output_images/fig_undst0.png "Undistorted Example"
[image3]: ./output_images/fig_unwarp0.png "Road Transformed"
[image4]: ./output_images/fig_colormapsBin0.png "Binarized Colormap"
[image5]: ./output_images/fig_sobelBin90.png "Binary Sobel"
[image6]: ./output_images/fig_slidingWindow0.png "Sliding Window"
[image7]: ./output_images/fig_pipelineAll.png "Binary Pipeline"
[image8]: ./output_images/fig_lanesfoundAll.png "Lanes Found for Test Images"
[video9]: ./output_images/fig_.mp4 "Video"

#### Sources 
Udacity SDC Nanodegree: [CarND-Advanced-Lane-Lines-P4](https://github.com/udacity/CarND-Advanced-Lane-Lines)

---

## Writeup / README

This is the writeup for my Udacity Self-Driving Car Nanodegree Term 1 [Project 4 submission](https://github.com/liangk7/CarND-Term1-Project4) in accordance with the [rubric guidelines](https://review.udacity.com/#!/rubrics/571/view)


### Camera Calibration

#### 1. Computing the Camera Matrix and Distortion Coefficients.

By using the samples images in the provided *camera_cal* folder, `obj points` and `img points` can be derived using `cv2.findChessboardCorners` and `cv2.drawChessboardCorners`, which get used in generating undistorted images.

![alt text][image1]

---

### Pipeline (images)

#### 1. Distortion Correction

Using the previously found parameters, `cv2.calibrateCamera` can be used to find additional `mtx` and `dst` parameters to perform `cv2.undistort` on any test image.

![alt text][image2]

#### 2. Perspective Transform

After removing any effects of camera distortion, we can then convert the image into an aerial view with `cv2.warpPerspective`. That does, however, require that we get a transform matrix and inverse transform matrix using `cv2.getPerspectiveTransformation` and predefined *source* and *destination* points. 

![alt text][image3]

#### 3. Threshold Binary Image using Color Transforms, Gradients, and other methods

A few of the Colormap options include:
* HSV - Hue, Saturation, Value
* HLS - Hue, Saturation, Lightness
* LAB - Lightness, A space (green-red, B space (blue-yellow)

![alt text][image4]

Approaches of Sobel gradient binarization include:
* Absolute value (x direction)
* Magnitude gradient (both x and y direction)
* Directional gradient (both x and y direction)

![alt text][image5]

#### 4. Lane Line Pixels and Polynomial Fit

As recommended in the instructional video, a histogram was employed to detect the likeliest lane line starting locations (bottom of aerial view image). By looking at the lower quadrants, we can omit any skew in data due to a curved lane (since the lane is straighter towards the bottom). After determining the initial rectangle position, the additional lane points can be found by searching immediately above the detected lane lines and shifting the rectangle positions according to the orientation of the detected points. 

![alt text][image6]

#### 5. Lane Curvature Radius and Vehicle Position

After establishing the image processing pipeline for lane detection, the lane curvature and vehicle position can be derived from the line polynomials and max vertical values. These values can be seen in the next step.

![alt text][image7]

#### 6. Results

With the image processing pipeline set up line charactericts calculated, we can apply it to the provided test images and test videos.

![alt text][image8]


---

### Pipeline (video)

#### 1. Final video output

[Link to video](INSERT HYPERLINK)


---

### Discussion



