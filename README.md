# SFND 2D Feature Tracking

<img src="images/keypoints.png" width="820" height="248" />

The idea of the camera course is to build a collision detection system - that's the overall goal for the Final Project. As a preparation for this, you will now build the feature tracking part and test various detector / descriptor combinations to see which ones perform best. This mid-term project consists of four parts:

## MP.1 Data Buffer Optimization
	
Implement a vector for dataBuffer objects whose size does not exceed a limit (e.g. 2 elements). This can be achieved by pushing in new elements on one end and removing elements on the other end.

## MP.2 Keypoint Detection
implement detectors HARRIS,  make it selectable by setting a string accordingly.

## MP.3 Keypoint Removal
Remove all keypoints outside of a pre-defined rectangle and only use the keypoints within the rectangle for further processing.

## MP.4 Keypoint Descriptors
Implement descriptors BRIEF, ORB, FREAK, AKAZE and SIFT and make them selectable by setting a string accordingly.

## MP.5 Descriptor Matching
Implement FLANN matching as well as k-nearest neighbor selection. Both methods must be selectable using the respective strings in the main function.
## MP.6 Descriptor Distance Ratio
Use the K-Nearest-Neighbor matching to implement the descriptor distance ratio test, which looks at the ratio of best vs. second-best match to decide whether to keep an associated pair of keypoints.
## MP.7 Performance Evaluation 1
Shi-Tomasi distribution looks good. Number of keypoints is good.  
Shi-Tomasi detection with n=1370 keypoints in 22.7936 ms  
Shi-Tomasi detection with n=1301 keypoints in 20.2346 ms  
Shi-Tomasi detection with n=1361 keypoints in 22.4203 ms  
Shi-Tomasi detection with n=1358 keypoints in 14.1898 ms  
Shi-Tomasi detection with n=1333 keypoints in 14.5625 ms  
Shi-Tomasi detection with n=1284 keypoints in 14.9884 ms  
Shi-Tomasi detection with n=1322 keypoints in 14.1135 ms  
Shi-Tomasi detection with n=1366 keypoints in 13.9777 ms  
Shi-Tomasi detection with n=1389 keypoints in 16.2458 ms  
Shi-Tomasi detection with n=1339 keypoints in 14.1036 ms  
  
Harris distribution looks good. Number of keypoints is small.  
Harris detection with n=53 keypoints in 5.68976e+16 ms  
Harris detection with n=62 keypoints in 5.68976e+16 ms  
Harris detection with n=63 keypoints in 5.6902e+16 ms  
Harris detection with n=69 keypoints in 5.69025e+16 ms  
Harris detection with n=82 keypoints in 5.69029e+16 ms  
Harris detection with n=73 keypoints in 5.69034e+16 ms  
Harris detection with n=69 keypoints in 5.69038e+16 ms  
Harris detection with n=108 keypoints in 5.69042e+16 ms  
Harris detection with n=81 keypoints in 5.69046e+16 ms  
Harris detection with n=68 keypoints in 5.69055e+16 ms  
  
FAST dsitribution looks good. Number of keypoints is good.  
FAST detector with n= 1824 keypoints in 1.2647 ms  
FAST detector with n= 1832 keypoints in 1.28409 ms  
FAST detector with n= 1810 keypoints in 1.18053 ms  
FAST detector with n= 1817 keypoints in 1.21591 ms  
FAST detector with n= 1793 keypoints in 1.20332 ms  
FAST detector with n= 1796 keypoints in 1.46795 ms  
FAST detector with n= 1788 keypoints in 1.17843 ms  
FAST detector with n= 1695 keypoints in 2.00197 ms  
FAST detector with n= 1749 keypoints in 1.18754 ms  
FAST detector with n= 1770 keypoints in 1.74414 ms  
  
BRISK distribution looks good. Number of keypoints is very large.  
BRISK detector with n= 2757 keypoints in 55.0969 ms  
BRISK detector with n= 2777 keypoints in 54.1485 ms  
BRISK detector with n= 2741 keypoints in 50.9518 ms  
BRISK detector with n= 2735 keypoints in 55.518 ms  
BRISK detector with n= 2757 keypoints in 56.8206 ms  
BRISK detector with n= 2695 keypoints in 51.0558 ms  
BRISK detector with n= 2715 keypoints in 53.201 ms  
BRISK detector with n= 2628 keypoints in 54.4504 ms  
BRISK detector with n= 2639 keypoints in 55.9129 ms  
BRISK detector with n= 2672 keypoints in 56.2565 ms  
  
ORB distribution looks good. Number of keypoints is limited by detector parameter.  
ORB detector with n= 500 keypoints in 15.3992 ms  
ORB detector with n= 500 keypoints in 16.5181 ms  
ORB detector with n= 500 keypoints in 10.328 ms  
ORB detector with n= 500 keypoints in 10.1773 ms  
ORB detector with n= 500 keypoints in 9.52496 ms  
ORB detector with n= 500 keypoints in 10.061 ms  
ORB detector with n= 500 keypoints in 12.664 ms  
ORB detector with n= 500 keypoints in 9.83195 ms  
ORB detector with n= 500 keypoints in 13.0553 ms  
ORB detector with n= 500 keypoints in 9.30359 ms  
  
AKAZE distribution looks good. Number of keypoints is good.  
AKAZE detector with n= 1351 keypoints in 104.222 ms  
AKAZE detector with n= 1327 keypoints in 103.469 ms  
AKAZE detector with n= 1311 keypoints in 91.5333 ms  
AKAZE detector with n= 1351 keypoints in 92.0802 ms  
AKAZE detector with n= 1360 keypoints in 114.41 ms  
AKAZE detector with n= 1347 keypoints in 104.118 ms  
AKAZE detector with n= 1363 keypoints in 90.8064 ms  
AKAZE detector with n= 1331 keypoints in 89.8814 ms  
AKAZE detector with n= 1357 keypoints in 89.0438 ms  
AKAZE detector with n= 1331 keypoints in 98.3149 ms  
  
SIFT distribution looks good. Number of keypoints is good.  
SIFT detector with n= 1437 keypoints in 197.566 ms  
SIFT detector with n= 1371 keypoints in 185.137 ms  
SIFT detector with n= 1380 keypoints in 217.426 ms  
SIFT detector with n= 1335 keypoints in 185.764 ms  
SIFT detector with n= 1303 keypoints in 187.244 ms  
SIFT detector with n= 1369 keypoints in 189.066 ms  
SIFT detector with n= 1396 keypoints in 185.757 ms  
SIFT detector with n= 1382 keypoints in 196.344 ms  
SIFT detector with n= 1463 keypoints in 196.297 ms  
SIFT detector with n= 1422 keypoints in 190.831 ms  

## MP.8 Performance Evaluation 2
	
Match count:
  
  BRISK-BRIEF: 1704

  BRISK-BRISK: 1570

  BRISK-FREAK: 1524

  BRISK-ORB: 1514

  AKAZE-BRIEF: 1266

  AKAZE-AKAZE: 1259

  AKAZE-BRISK: 1215

  AKAZE-FREAK: 1187

  AKAZE-ORB: 1182

  FAST-BRIEF: 1099

  FAST-ORB: 1071

  SHITOMASI-BRIEF: 944

  SHITOMASI-ORB: 908

  FAST-BRISK: 899

  FAST-FREAK: 878

  SHITOMASI-FREAK: 768

  SHITOMASI-BRISK: 767

  ORB-ORB: 763

  ORB-BRISK: 751

  SIFT-BRIEF: 702

  SIFT-FREAK: 593

  SIFT-BRISK: 592

  ORB-BRIEF: 545

  ORB-FREAK: 420

  HARRIS-ORB: 146

  HARRIS-BRIEF: 146

  HARRIS-BRISK: 129

  HARRIS-FREAK: 128
  

## MP.9 Performance Evaluation 3
Average processing time:

  FAST-BRIEF: 0.00111163

  FAST-ORB: 0.00127987

  
  ORB-BRIEF: 0.00399563
  
  HARRIS-BRIEF: 0.00518273
  
  SHITOMASI-BRIEF: 0.00528867
  
  HARRIS-ORB: 0.00540922
  
  SHITOMASI-ORB: 0.00569296
  
  ORB-ORB: 0.00579009
  
  FAST-FREAK: 0.0182116
  
  ORB-FREAK: 0.0206931
  
  HARRIS-FREAK: 0.0220074
  
  SHITOMASI-FREAK: 0.0225976
  
  AKAZE-BRIEF: 0.0253003
  
  AKAZE-ORB: 0.0256869
  
  AKAZE-FREAK: 0.0427824
  
  AKAZE-AKAZE: 0.0457293
  
  SIFT-BRIEF: 0.0492739
  
  SIFT-FREAK: 0.06207
  
  FAST-BRISK: 0.123742
  
  ORB-BRISK: 0.126471
  
  HARRIS-BRISK: 0.127705
  
  SHITOMASI-BRISK: 0.129107
  
 
  BRISK-BRIEF: 0.144472
  
  BRISK-ORB: 0.146229
  
  AKAZE-BRISK: 0.147496
  
  BRISK-FREAK: 0.162551
  
  SIFT-BRISK: 0.172018
  
  BRISK-BRISK: 0.267362

The 3 best detector-descriptors are FAST-BRIEF, FAST-ORB, ORB-BRIEF.





