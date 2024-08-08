# Expressionet

An AI model that can detect one's emotions through his(her) expressions.

![happiness](https://github.com/user-attachments/assets/92d87de1-f5cf-4102-ad92-d4c7dba500d1)
![sadness](https://github.com/user-attachments/assets/46550dca-6ded-4c39-ab01-cbb7563ec1b9)
![disgust](https://github.com/user-attachments/assets/c9da4113-9a09-47b4-8176-249595b8495b)

## The Algorithm

Expressionet was trained by using a dataset in kaggle called "6 Human Emotions for image classification" (link: https://www.kaggle.com/datasets/yousefmohamed20/sentiment-images-classifier/datauses). You can use an image as a input. After downloading the images to VS Code and typing certain command, Expressionet can process the images and show the possible emotions of the people in them, by using Imagenet as a form basis. You can also use webcam to get the expressions of the peoble in the frame of the webcam, so Expressionet can show those people's possible moods live. This project would have great impact in electronic devices and intellident robots. By installing this AI model into those devices, they can get the users' emothions live and easily, so that they can give users better experiences.

## Running this project

1. Setup and install Jetson Nano and VScode.
2. Connect jetson Nano to your computer hotpot, write down your Jetson Nano's IP for later use.
3. Connect your VScode to your Jetson Nano with "ssh nvidia@IPAddress' (the password is "nvidia").
4. Open the NVIDIA home folder.
5. Open terminal and use the command below to enter the needed directory.\
   `cd jetson-inference/python/training/classification`
6. Use the two commands below to set NET and DATASET for later use. Replace "FOLDER_NAME" with whatever the file you create.\
   `NET=models/FOLDER_NAME`\
   `DATASET=data/FOLDER_NAME`
7. Move the picture, which you want to try in this AI model, into "classificaton" folder.
8. Run the model by using this command. Don't forget to replace "IMAGE_RELATIVE_PATH" with the relative path of your image and replace "IMAGE_OUTPUT_NAME" with your wanted name of the output image.\
   `imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt IMAGE_RELATIVE_PATH IMAGE_OUTPUT_NAME`\
Here is an example:\
   `imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/cat/01.jpg cat.jpg`\
10. Also, you can replace the "IMAGE_RELATIVE_PATH IMAGE_OUTPUT_NAME" with `/dev/video0 webrtc://@:8554/output` after connecting your webcam with your Jetson Nano, and type `IPAddress:8554` in a new Google tab, so that the input images will become the images captured by the webcam and you can see the output images live.
    
Link to the introduction video of this project: `https://youtu.be/adIz0eZWXfc`
