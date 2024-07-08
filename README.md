First, it loads the first 5 extracted frames from the list of frame paths and reads
its dimensions. Then, it undistorts the image using the camera matrix (mtx), distortion coeffi-
cients (dist), and optional rectification transformation (None) obtained during calibration. Next,
it draws the detected chessboard corners on the original image using cv2.drawChessboardCorners()
before calibration and draws the corresponding corners after calibration on the undistorted image.
Finally, it displays both the original and undistorted images side by side using matplotlib.pyplot.

![image](https://github.com/saidineshgelam/Depth-estimation-using-Stereo-Vision-/assets/144295692/d92145c8-19c6-4da2-b187-e93199491ecf)

detects keypoints and computes descriptors for two con-
secutive images using the SIFT (Scale-Invariant Feature Transform) algorithm, matches descriptors
between the images using the brute-force matcher, applies a ratio test to select good matches, draws
the matches between the images, and displays the matches.
converts keypoints from two images to numpy arrays, estimates the Fundamental matrix using the
RANSAC algorithm, and optionally filters out outliers using the obtained mask. The Fundamental
matrix represents the epipolar geometry between two images and is used for matching keypoints
and finding corresponding points between them.
.
![image](https://github.com/saidineshgelam/Depth-estimation-using-Stereo-Vision-/assets/144295692/3792fd2d-4d87-4a28-a145-3b073989be32)

It takes the rectified images, epipolar lines, and corresponding keypoints as input and returns the
images with epipolar lines and feature points drawn in color. Each line is drawn from the left image
to the right image, and keypoints are marked with circles. Random colors are assigned to each line
for visualization.
Rectifies two images using perspective transformation with the provided homog-
raphy matrices H1 and H2, converts them to grayscale, computes epipolar lines for the rectified
keypoints, draws the epipolar lines on the rectified images, and finally concatenates the images
horizontally for visualization. The result shows the rectified images with horizontal epipolar lines
drawn on them, indicating the correspondence between the points in the rectified images.

![image](https://github.com/saidineshgelam/Depth-estimation-using-Stereo-Vision-/assets/144295692/856d19b0-c915-488f-b7f5-42f2bc7c5797)

defines a function disparity_and_depth() to compute the depth map and array
depth from a given baseline, focal length, and disparity map. It then computes the disparity map
using the StereoBM algorithm, normalizes it, and computes the depth map and array depth. Finally,
it displays the disparity map, depth map in color, and depth map in grayscale for visualization.
