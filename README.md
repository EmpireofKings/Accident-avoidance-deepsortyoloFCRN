# Accident-avoidance-deepsortyoloFCRN
An accident avoidance program that raises alert when nearby vehicles are moving at a relative speed faster than a threshold value, additionally it logs some data onto NEM-Mijin blockchain network.

The program works in the following few steps:
* The video feed is processed frame by frame where depth maps for each frame is produced. 
- Using deep-sort and YOLO3 tracking algorithm, the vehicles are tracked frame by frame. The bounding box centroid coordinates are used to find the depth of the car.
- The relative change in depth of every vehicle is calculated frame by frame and then divided by FPS(depending on processor speed). This will provide relative velocity of the vehicles
- This relative velocity is used to raise alert (when above a hardcoded threshold value).
- This speed along with tracking_id is then logged onto a NEM blockchain network through a server hosted on local machine.

Dependencies can be downloaded from https://github.com/iro-cp/FCRN-DepthPrediction and https://github.com/Qidian213/deep_sort_yolov3
Server file has been added.Run server in a new terminal window.
To run the program type python dmo.py (also write the path to the video file in dmo script)
