Calibration process
1. Collect images from camera attached to robot arm and its corresponding end-effector pose
2. Run cameraCalibrator on Matlab with collected images and generate script
3. Copy the last four lines from main_calibrate_camera.m to the generated script
4. Run main_reproject_calib_result.ipynb to generate text files for robot pose to run visp_handeye_calibrator
5. Run handeye_calibration ROS package (visp)
6. Run main_reproject_calib_result.ipynb to check results