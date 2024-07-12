
# Innovative TeleICU system using Deep Learning approaches

The TeleICU system is designed to enhance the quality and efficiency of intensive care units (ICUs) by leveraging advanced deep learning techniques. This innovative system aims to address critical challenges in patient monitoring, diagnosis, and treatment within ICUs by providing real-time analysis and actionable insights through video feeds and other data sources.

## Screenshots

![Thumbnail](https://github.com/user-attachments/assets/71140960-f53e-4f57-85d5-2a8c8f497985)

# Key Components:

Real-Time Video Analysis:

YOLO Model for Object Detection: Utilizing the YOLO Nano-S model, the system can detect and track patient movements, medical staff activities, and equipment usage in real-time. This ensures continuous monitoring of patient conditions and immediate identification of any irregularities or emergencies.

TensorFlow and PyTorch: These frameworks support the deployment of complex deep learning models that process and analyze video data, enabling accurate detection and classification tasks.
Image and Signal Processing:

OpenCV and NumPy: These libraries are employed for efficient image processing tasks, such as enhancing video quality, detecting vital signs, and analyzing physiological signals.

EasyOCR: This tool is used for extracting text information from medical documents, charts, and equipment displays, aiding in the digitalization and analysis of handwritten or printed information.

Progress Tracking and Alerts: Real-time analysis results are presented through the interface, providing instant alerts and progress updates to medical staff. This facilitates timely interventions and better patient management.
Data Management and Collection:

Efficient Data Handling: The system uses Python’s standard libraries such as time and collections for managing time-sensitive tasks and organizing data, ensuring smooth and efficient operation.



## Installation(to be run locally)

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install required packages in your vscode terminal.

Make sure to do it in a virtual environment (to as not to get any conflict errors)

Also make sure to have "Python Version >=3.8".
```bash
pip install opencv-python numpy tensorflow torch easyocr ultralytics

```


# 🚀 Demo Video:

(https://youtu.be/bOGAz2fB9wI)




## Features

- Intensivity Detection
- Chest Pain Detection
- Fall Detection
- Vital Sign Alert System (Experimental)

Intensivity Detection:

Model: YOLOv8 (best_small.pt)
Functionality: This model is designed to detect individuals within an ICU setting, distinguishing between different categories such as intensities, family members, and patients. By processing video frames with an input shape of (1, 3, 640, 640), the model helps in identifying and tracking the presence of these entities in real-time. This is crucial for monitoring the ICU environment and ensuring that only authorized personnel are present.

Chest Pain Detection:

Model: YOLO Nano-S (best_chest.pt)
Functionality: This model scans every 3rd frame of the video feed to detect signs of chest pain in patients. If the model identifies a chest pain indication within a patient bounding box for a continuous duration of 3 seconds, it triggers an alert. The input shape for this model is (1, 3, 416, 416). This feature is essential for promptly responding to critical conditions and providing immediate medical attention.

Fall Detection:

Model: PoseNet 2.0 (tflite-model-maker-falldetect-model.tflite)
Functionality: The fall detection model uses PoseNet 2.0 to analyze every 3rd frame for any indications of a fall. By monitoring the patient's posture and movements, it can accurately detect falls and subsequently trigger alerts to ensure quick response times. This feature is vital for preventing injuries and ensuring patient safety.

Vital Signs Detection:

Models:

- YOLOv8 for Monitor Detection (best_monitor.pt).

- YOLOv8 for Vitals Detection (best_vitals-2.pt).

Functionality: This dual-model setup is designed to monitor the patient's vital signs. The monitor detection model identifies the monitor within the frame, while the vitals detection model focuses on the vital sign readings displayed on the monitor. 

Both models process every 3rd frame with an input shape of (1, 3, 416, 416). Using EasyOCR, the system reads the heart rate (HR) from the bounding box. 

If the HR value is below 60 or above 155, an alert is triggered, indicating potential medical issues that require attention. This feature ensures continuous and accurate monitoring of vital signs, crucial for patient health management.

## Documentation

The inner working and architecure of the models used in this system are all described in the "Intel Unnati _ Idea Submission" file.

And the configuration, version details and dataset used are in the "details.txt".

And ipnyb file to "convert .pt files to .onnx files" is also available in repo in "onyx_conversion.ipynb".


## Running Tests

To run tests:

- Download the github repo.
- Extract the folders from it.
- Open VScode and in the open folder section select the downloaded github folder.
- Enable Virtual Environment in VScode.
- Install the libraries said in the Installation section.
- Run the "TeleICU_main.ipynb" and run the function that you want.

To test new videos:

- In the github repo folder, search for vids folder.
- Input your video.mp4 file in there.
- Go to the function that you want to run and change the filename and run the function.
eg- 'vids/Doc.mp4', change the video -> 'vids/yourfile.mp4'

- Now the new video should work now.




## Contributing

Contributions are always welcome!

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[GNU](https://www.gnu.org/licenses/gpl-3.0.en.html#license-text)
