# Facial-Recognition-and-Temperature-Monitoring-System

Base features:

* Real-time face detection using the Raspberry PiCam 5M and OpenCV Haarcascades frontal face detection.
* Facial recognition using Davis King's dlib library. 
* Temperature measurements using a combination of the MLX90614 and AMG8833 infrared sensors.
Added features:
* GPU accelerated (CUDA) computing using the Google Virtual Machine's NVIDIA Tesla K80.
* Option to encode faces using either 68 facial landmarks or 81 facial landmarks. More landmarks result in higher accuracy at the expense of processing time.
* Option to train the model to detect using either Histogram of Oriented Gradients (HOG) or Convolutional Neural Network (CNN). CNN is much more accurate and suitable for datasets with a large number of different faces.
*  Image preprocessing and standardization using gamma correction and face alignment.
* Restricted the system to process only one face at a time (within the red ellipse) even if multiple faces are detected. The image is then sent to the Google virtual machine which again checks for faces (to prevent/minimize false positives) and does the face recognition plus google cloud storage uploads.
* Estimation of body core temperature using a simple algorithm which takes into consideration the skin temperature, ambient temperature, and average skin surface temperature. Loosely based on https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1752199/
* Average skin temperature is estimated using bicubic interpolation of the AMG8833's 8x8 sensor array output. 
* PyQt5 GUI for ease of use. The terminal of the google cloud virtual machine is embedded into the GUI to facilitate access and monitoring all through the Raspberry Pi.
* Automated storage and record keeping using Google Cloud Storage with timestamps and temperature stamps for users.
* 7" touchscreen for easy local access.
* Virtual Network Computing (VNC) enabled for easy remote access.
* All data transfers are carried out through a secure VPN tunnel, SSH, and TCP.

Please refer to the "Demo.gif" and "animation.gif" files for a brief preview. The programming scripts will be uploaded in the near future.
