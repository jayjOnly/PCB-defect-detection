<h1> README - YOLOv7 Fine-tuning for PCB Defect Detection </h1>
<h2> Project Overview </h2>
This project focuses on fine-tuning the YOLOv7 (You Only Look Once version 7) model to detect defects in printed circuit boards (PCBs). By leveraging the powerful object detection capabilities of YOLOv7, we aim to identify and classify various types of defects in PCBs, such as missing components, misalignments, soldering issues, and other manufacturing errors. The fine-tuned model can be deployed in real-world manufacturing pipelines for automated quality control and defect detection.

<h2>Requirements</h2>
To run the project, ensure the following dependencies are installed: <br>
1. Python 3.8+ <br>
2. PyTorch 1.10+ <br>
3. CUDA (for GPU acceleration) <br>
4. YOLOv7 Repository (clone from official GitHub) (https://github.com/WongKinYiu/yolov7.git) <br>
5. Numpy <br>
6. Matplotlib <br>

<h2>Training the Model</h2>
To fine-tune YOLOv7, follow these steps:
1. Download the pre-trained YOLOv7 weights from the official repository.
2. Modify the config/pcb.yaml file to match the number of classes and dataset paths.
3. Run the training script:
   `python Code/train.py --config config/pcb.yaml --weights models/yolov7.pt --epochs 100`

Note: config and pre-trained model can be download https://github.com/WongKinYiu/yolov7/tree/main/cfg/training

<h2>Test</h2>
To test the model's performance on the validation set, run:

`python Code/test.py --weights models/best.pt --data data/valid/`

<h2>Detect</h2>
To try the model's on real time via webcam, run:

`python detect.py --weights best.pt --source 0`

Note: Make sure you model's name and path before declare in the weight parameter
