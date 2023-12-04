# ReadMe | ESE8 | Embedded-Computer Vision Project

Setting up TensorFlow Lite on the Raspberry Pi :

1. Update the Raspberry Pi.
2. Download this repository and create a virtual environment.
3. Install TensorFlow and OpenCV.
4. Set up the TensorFlow Lite detection model.
5. Run the TensorFlow Lite model !

- 👉 Step1 : **Update the Raspberry Pi by running the following commands in the terminal:**
    
    ```jsx
    sudo apt-get update
    sudo apt-get upgrade
    ```
    
- 👉 Step2 : **Make sure the camera interface is enabled in Raspberry Pi Configuration menu.**
    
    ![Screenshot 2023-05-05 at 6.16.32 PM.png](ReadMe%20ESE8%20Embedded%20Project%200d1eec4c178540599843868253f10fc6/Screenshot_2023-05-05_at_6.16.32_PM.png)
    
- 👉 Step3 : **Download this repository and create virtual environment**
    
    ```jsx
    git clone https://github.com/AbhishekG-1plus/ObjectDetection.git
    ```
    
    Renaming for simplifying purposes:
    
    ```
    mv TensorFlow-Lite-Object-Detection-on-Android-and-Raspberry-Pi tflite1
    cd tflite1
    ```
    
- 👉 Step4 :  **Create A Virtual Environment**
    
    We will be using a virtual environment for this guide because it prevents any conflicts between versions of package libraries that may already be installed on your Pi. By keeping TensorFlow installed in its own environment, we can avoid version conflicts and ensure that everything works smoothly.
    
    Install virtual-env by issuing:
    
    ```jsx
    sudo pip3 install virtualenv
    
    ```
    
    Then, create the "tflite2-env" virtual environment by issuing:
    
    ```jsx
    python3 -m venv tflite2-env
    ```
    
    Activate the environment:
    
    ```jsx
    source tflite1-env/bin/activate
    ```
    
- 👉 Step5 :  **Install TensorFlow Lite dependencies and OpenCV**
    
    The bash script automatically downloads all the correct dependencies we require in this project including OpenCV:
    
    ```jsx
    bash get_pi_requirements.sh
    ```
    
- 👉 Step6 : **Set up TensorFlow Lite detection model**
    
    **Using Google's sample TFLite model**
    
    Google provides a sample quantized SSDLite-MobileNet-v2 object detection model which is trained off the MSCOCO dataset and converted to run on TensorFlow Lite. It can detect and identify 80 different common objects, such as people, cars, cups, etc.
    
    Download the sample model by issuing:
    
    ```jsx
    wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/coco_ssd_mobilenet_v1_1.0_quant_2018_06_29.zip
    ```
    
    Unzip it to a folder called "Sample_TFLite_model" by issuing (this command automatically creates the folder):
    
    ```jsx
    unzip coco_ssd_mobilenet_v1_1.0_quant_2018_06_29.zip -d Sample_TFLite_model
    ```
    
- 👉 Step6 : **Run TensorFlow Lite detection model.**
    
    The TFLite_detection_webcam.py script will work with either a Picamera or a USB webcam.
    
    ```jsx
    python3 TFLite_detection_webcam.py --modeldir=Sample_TFLite_model
    ```
    
    HOLA! OBJECT DETECTED! YOU ARE A PERSON! xd
    
    ![Screenshot 2023-05-05 at 6.37.22 PM.png](ReadMe%20ESE8%20Embedded%20Project%200d1eec4c178540599843868253f10fc6/Screenshot_2023-05-05_at_6.37.22_PM.png)
    

<aside>
💡 A complete video of the demonstration:

</aside>

[https://photos.app.goo.gl/y6JhqgtntCbR5oCPA](https://photos.app.goo.gl/y6JhqgtntCbR5oCPA)
