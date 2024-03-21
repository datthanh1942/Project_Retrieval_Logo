# Project_Retrieval_Logo
## The source code is executed and run on Google Colab with the required libraries installed, such as:
- ultralytics
- CUDA (có thể không cần nhưng chạy và xử lý chậm hơn)
## The necessary files to run for the functions are:
- Detect: last.pt (the result of the last training epoch) or best.pt (the result of the best training epoch)
- Retrieval: new_cluster.pkl (the feature vector file that has been labeled of the dataset)
(Download link: https://drive.google.com/file/d/1---ViJ3rPYKDSVxjZY-VloY5Fpy8qruv/view?usp=drive_link)

### The “Train_YOLO” folder is the source code and file leading to the necessary dataset to train YOLO “logo_detect_yolov8.yaml”, you need to follow the path below to get the .pt file:
* Source/Train_Yolo/runs/detect/train/weights/*.pt

### The “Normalize” file is the data preprocessing process for the YOLO training dataset

## The running process of the main source code “Project” is:
- Run ‘detect logo’ to get the logo cut image from the input image
- Then proceed to run the functions to extract features from the dataset (train folder)
- Call the model you want to use
- Cluster and label the dataset using the KMeans algorithm
- Save or reload the clustered feature vectors of the dataset using .pkl
- Take the logo image that has been cut from ‘detect logo’ to extract features and predict labels
- Use the feature vector of the input image to compare with the images with the same label
- Sort the similarity in descending order and take the top_k results
- Print out the similarity and the similar images in the result folder

## Link dataset
- Data train YOLO: https://drive.google.com/drive/folders/1IuMtSq-N3_ovanwRtj9qgmeRbEfid3S5?usp=drive_link
- Dataset train retrieval: https://drive.google.com/drive/folders/1PsdiHlxHFq2hfHBXd7PEdZ3ZrlHuz5uU?usp=sharing

## Link demo
* https://drive.google.com/file/d/1UODcUUQNLn5hoOLuIlyovyfMRKGRTdRx/view?usp=sharing
