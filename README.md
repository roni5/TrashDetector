# TrashDetector
- automatic trash separator using yolo

## Development Intention
- Before explaining, this is my Capstone Design Results.
- Garbage is being dumped indiscriminately(thoughtless) on the campus.
- If it is thrown away without recycling, it will take a lot of time and manpower to classify it, so recycling is not possible now.
- So we developed the Trash Detector that encourages students to throw garbage into trash cans.

# Hardware

- Raspberry 3b+
- Motor Driver - pca9685
- Servo moter - mg996r
- Unused smartphone - samsung galaxy s7

## Connection Diagram
![1589167164935](https://user-images.githubusercontent.com/53466091/91026802-3892f900-e636-11ea-9e9b-e6519950bee6.png)

## Inner Hardware Configuration
Servo moter and moter driver
![20200508_195537](https://user-images.githubusercontent.com/53466091/91027383-fcac6380-e636-11ea-9424-eaf537971ad9.jpg)
![20200508_205410](https://user-images.githubusercontent.com/53466091/91027385-fe762700-e636-11ea-9be5-1b1677147578.jpg)

# Test Operation Videos

## Four directions
[![Four directions](http://img.youtube.com/vi/BxDGZi_dKDQ/0.jpg)](https://youtu.be/BxDGZi_dKDQ?t=0s)
## Seperating garbage collection Without detection
[![Four directions](http://img.youtube.com/vi/oi0hDlDZYZc/0.jpg)](https://youtu.be/oi0hDlDZYZc?t=0s)
## Face video & making images for train dataset
[![Four directions](http://img.youtube.com/vi/hRKlib9sNXQ/0.jpg)](https://youtu.be/hRKlib9sNXQ?t=0s)
##
![그림1](https://user-images.githubusercontent.com/53466091/91062642-ec60ac80-e667-11ea-9b60-bf122a3cbf4c.png)
![그림2](https://user-images.githubusercontent.com/53466091/91062636-ea96e900-e667-11ea-999b-47967fbf73e8.png)
## Face detection
[![Four directions](http://img.youtube.com/vi/YgaPjcbiClU/0.jpg)](https://youtu.be/YgaPjcbiClU?t=0s)

# Presentation Video (korean)
[![Four directions](http://img.youtube.com/vi/8UlOWuIw0yQ/0.jpg)](https://youtu.be/8UlOWuIw0yQ?t=0s)


# Environments
- Raspbian OS
- python 3.6
- Opencv
- MTCNN

# How to use

## Face Detection

- First, We receive a full face video from the user, which is about 10 to 20 seconds.
- Second, in per_frame_video.py, we can split the video into a frame and save it as an image. This becomes train dataset.
- Third, in boxing.py, The mtcnn module produces an xml file whith store facial coordinates and multiple information in all images.
- The xml file is not appropriate because we are going to use yolo. Therefore, convert all xml files into txt files, i.e. yolo format. (in xml_to_yolo.py)
- And then, we already construct train dataset(face dataset), train it!

## Trash Detection (NOT USAGE, WHAT I DO)
- We collected 4,000 images from the kagle, 2,000 images from the local dataset taken by ourselves, and 2,000 images from the coil dataset to form the garbage dataset.
- So, I labelled all 8,000 images myself. 
- And, train it!

## files
- detection_dnn.py is detect the object and counts what kind of the trash is and returns the nearest classification(ex. plastic, paper, can.. etc).
- detection_face.py is detect the face, counts whose face it is close to, and returns the person who counts the most.
- ctr_final.py is the main file of this project. in this file, it detect the face and checks who throws it away, checks which garbage is, gives the user a reward, runs motor control, and collects it separately.

# Notice
- In my repository there is no weights files, because they are heavy files. If you want our trained weights, contect me.
- Because I was in charge of object detection, I am not well aware of the applications and servers, databases, and motor control used.

# Contect
- wkdrudtn1@gmail.com




