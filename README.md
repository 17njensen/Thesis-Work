<h1 align="center">GPS-Denied Navigation Using LiDAR/Imagery and Digital Surface Model Creation</h1>
<h3 align="center">This project is my current thesis work at Utah State University, where I am pursuing my master's in Electrical engineering with a focus in signal processing for geospatial data</h3>

This project is build off of the original work done at the Center of Advanced Imagery and LADAR (CAIL), involving using LiDAR and camera fusion to create digital surface models (DEM) using methods of advanced signal and image processing. This system is attached to a drone (sUAS) and the data is captured during a flight. It shall be noted that this data was captured using a low-cost LiDAR sensor, camera, and other sensors. Below is an examle of the imagery and how it is processed. 



First, the LiDAR is captured, and projected into a world-space frame so imagery can be overlaid onto the point cloud. This image represents an example of the captured LiDAR data for a parking lot near a marina.
<p align="center">
  <img src="https://github.com/17njensen/Thesis-Work/blob/main/Swaths300.bmp" />
</p>
Next, the using a method of triangulation between multiple scans and points, a wireframe is made for texturizing the surface of the data.
<p align="center">
  <img src="https://github.com/17njensen/Thesis-Work/blob/main/Swaths300_wire.bmp" />
</p>
Lastly, the imagery is overlaid onto the created surface to give visiblity into what data is captured. 
<p align="center">
  <img src="https://github.com/17njensen/Thesis-Work/blob/main/Swaths300_final.PNG" />
</p>
Publications from CAIl of the process can be found here: [Three-dimensional image reconstruction using bundle adjustment applied to multiple texel images](https://www.spiedigitallibrary.org/conference-proceedings-of-spie/9832/1/Three-dimensional-image-reconstruction-using-bundle-adjustment-applied-to-multiple/10.1117/12.2223259.full?SSO=1)
and here: [Method for 3-D Scene Reconstruction Using Fused LiDAR and Imagery From a Texel Camera](https://www.researchgate.net/publication/334382609_Method_for_3-D_Scene_Reconstruction_Using_Fused_LiDAR_and_Imagery_From_a_Texel_Camera)
<h4 align="center">
  GPS-D Navigation using LiDAR/Imagery
</h4>
For the purpose of my thesis work, during this process, the addition of location estimation was made. This involved taking IMU data from the device, and using the fused LiDAR and camera data for additional assistance in location estimation, due to sensor drift and low-cost accuracy. To do this, a Extended Kalman Filter is used for position estimation, as well as a gradient descent algorithm called the Levenberg-Marqurdt algorithm, that processes the estimated pose and position with the fused Imagery/LiDAR and outputs a corrected pose and position for the Extended Kalman Filter. Below is the block diagram.

<p align="center">
  <img src="https://github.com/17njensen/Thesis-Work/blob/main/gpsd_block_diagram.PNG" />
</p>

The results so far are as seen in the image below. This is currently a work in progress. 
<p align="center">
  <img src="https://github.com/17njensen/Thesis-Work/blob/main/map.png" />
</p>

<h4 align="center">
  Feature Detection
</h4>

One of the side projects that was persued for a moment, was feature detection. This involved using the LiDAR and imagery to extract information from the data captures during a recorded flight. This effort was later scrapped due to time constraints and focus on my thesis work. Some of the my efforts can be seen below:

This was the extraction and differentiation of tree canopies and surrounding vegetation versus the grassy flat areas for the rest of the scan.
<p align="center">
  <img src="https://github.com/17njensen/Thesis-Work/blob/main/feature_detection.PNG" />
</p>

This was the extraction of a road versus the vegetation surrounding the road. It can be noted that these were not perfect results, but given more time and effort, these results could be further improved. 
<p align="center">
  <img src="https://github.com/17njensen/Thesis-Work/blob/main/8520_variance_alg.bmp" />
</p>
