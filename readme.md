TRAFFIC SIGNS RECOGNITION USING THE YOLO ALGORITHM

![306497416](https://user-images.githubusercontent.com/53332753/126833194-a648432d-a450-49e3-9fcc-479455990a48.jpg)



How to implement the identification of traffic signs From labeling to training using Google Colaboratory and Yolov5

FIRST STEP: GATHERING DATASET

in the first step, I downloaded the information I needed, to create my dataset from photos of the following address.
https://www.mapillary.com/dataset/trafficsign

I used the labelimg tool to label my photos


SECOND STEP: USING LABELIMG

To use labelimg, we must first install it, which is easily done with the following command (windows cmd ) :
pip install labelimg
After installing the labelimg we must open it, but there is one thing that can make using labelimg much easier.
classifying your files before opening labelimg
for example, in this project, we have 10 classes, so at first, we create a text file and write our classes in it
like this:
Sign_No_Stopping

Sign_Stop

Sign_No_parking

Sign_No_Entry

Sign_Bend_To_Right

Sign_crossing

Sign_Give_way

Sign_Turn_left

Sign_bump

Sign_No_Overtaking

You can downoad my labeled dataset using the link below

https://drive.google.com/file/d/1iQwsS8R8Me4TyuvDYpcPrpJ12yxNwyVi/view?usp=sharing


Now we can open labelimg using this command:
Labelimg <images directory> <classes.txt directory>
  
there are two things that we must consider while using labelimg
first, make sure you've selected the YOLO
and the second, to save txt file after labeling
  ![image](https://user-images.githubusercontent.com/53332753/126833314-68ed7520-f4ec-451c-992c-ac0bbad2fb24.png)

  After labeling all our files we should split them into three root folders:
Train, val (valid), test
And in each folder, we must separate labels (text files) and images
  After reviewing nearly 7,000 random images, I collected about 1,000 labeled images for use in my train, valid, and test.
when data collection is done, we must zip all three files and upload them to Google Drive to be able to reach them using Google Colaboratory.
  
THIRD STEP: GOOGLE COLABORATORY
In the Google Colab environment, we need to do the following actions  
  ![image](https://user-images.githubusercontent.com/53332753/126833474-255437e4-ad7e-4d3c-9e8b-36c9e052d1fe.png)
  
  The command will install the dependencies
  
  After installing the dependencies we must install GPU use
  ![image](https://user-images.githubusercontent.com/53332753/126833552-0d1f6807-3d65-470c-b063-3a568e24c2e2.png)

 After doing the above steps, a folder named yolov5 should be created in the files section
  ![image](https://user-images.githubusercontent.com/53332753/126833580-15fafe5c-1dc6-425b-90ed-f94306bea64a.png)

  To examine what kind of GPU has been allocated for us, we can use the following command
  ![image](https://user-images.githubusercontent.com/53332753/126833609-952dda0a-b52f-4390-b5df-0570cc18f052.png)

  Now we must mount our Google Drive account to Google colab
![image](https://user-images.githubusercontent.com/53332753/126833622-4c3ac6cd-4660-4bf9-8d37-dbdbb9ab8b19.png)

  To access our images file we should unzip it in colab using !unzip command
  
  Do not forget to create the yaml file as well
To create this file, we can create a YAML file in our system using Notepad and then change its format to .yaml
The file must contain the number of classes, class names, and the address of the val and train folder

Yaml requirements are listed in ipynb files
  
The most important part is here training
with following code we start the training
  ![image](https://user-images.githubusercontent.com/53332753/126833906-cd27a6d9-8ded-42b2-bbbd-b21300a98a43.png)

 after 7 hours of training, I faced this error
  
![image](https://user-images.githubusercontent.com/53332753/126833932-ee6e105e-6e66-4dc0-b35e-a83aea796600.png)

so I switched to another account and did the rest of the training there
As I had saved the checkpoints
I resumed the training from where it had stopped with the following command
  
![image](https://user-images.githubusercontent.com/53332753/126833947-6cc64f15-6377-4c4d-b067-fefa48857098.png)
  
  when training is done we can see the Tensorboard using the following command
  ![image](https://user-images.githubusercontent.com/53332753/126834027-e75b238b-15cb-4dcd-a594-6615f2b6adcc.png)

  ![image](https://user-images.githubusercontent.com/53332753/126834061-5fd4682a-da4b-44b9-9316-203ce68faf4f.png)

  
  Output:
  
  
![image](https://user-images.githubusercontent.com/53332753/126834111-06e50372-8acb-4ae5-8cab-b5f84f73bf1f.png) ![image](https://user-images.githubusercontent.com/53332753/126834126-7e852924-1846-4a31-8dd9-8dc9020ac02d.png) ![image](https://user-images.githubusercontent.com/53332753/126834149-cf062522-ddfd-431a-9b15-09c6338f0a19.png) ![image](https://user-images.githubusercontent.com/53332753/126834101-b4a1a273-d166-473f-933a-4abe24c3b115.png) 

Thanks for your attention

Welcome_To_Colaboratory (0) = Googlecolab environment code before gpu limit expires
Welcome_To_Colaboratory = Googlecolab environment code after changing account
exp = Output test files
 
  
