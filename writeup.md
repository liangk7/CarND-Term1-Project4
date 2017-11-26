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

[image1]: ./examples/undistort_output.png "Undistorted"
[image2]: ./test_images/test1.jpg "Road Transformed"
[image3]: ./examples/binary_combo_example.jpg "Binary Example"
[image4]: ./examples/warped_straight_lines.jpg "Warp Example"
[image5]: ./examples/color_fit_lines.jpg "Fit Visual"
[image6]: ./examples/example_output.jpg "Output"
[video1]: ./project_video.mp4 "Video"

#### Sources 
Udacity SDC Nanodegree: [CarND-Advanced-Lane-Lines-P4](https://github.com/udacity/CarND-Advanced-Lane-Lines)

---

## Writeup / README

This is the writeup for my Udacity Self-Driving Car Nanodegree Term 1 [Project 4 submission](https://github.com/liangk7/CarND-Term1-Project4) in accordance with the [rubric guidelines](https://review.udacity.com/#!/rubrics/571/view)


### Camera Calibration

#### 1. Computing the Camera Matrix and Distortion Coefficients.

![alt text][image1]

---

### Pipeline (images)

#### 1. Distortion Correction

![alt text][image2]

#### 2. Threshold Binary Image using Color Transforms, Gradients, and other methods

![alt text][image3]

#### 3. Perspective Transform

![alt text][image4]

#### 4. Lane Line Pixels and Polynomial Fit

![alt text][image5]

#### 5. Lane Curvature Radius and Vehicle Position

![alt text][image6]

#### 6. Results

![alt text][image7]


---

### Pipeline (video)

#### 1. Final video output

[Link to video](INSERT HYPERLINK)


---

### Discussion



