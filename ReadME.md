
<a href="https://colab.research.google.com/github/aradjabova/dsc-mod-4-project-v2-1-online-ds-ft-120919/blob/master/ReadME.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>


# Pneumonia Image Classification

Using the OSEM process we will build a image classifier to predict if a patient has pneumonia (based on their x-rays). We are building this model in the hope of reducing human error in reading the x-rays of patients. 

This is an unbalanced binary-class classification problem; because of this we will be creating addition augmented photos of the normal lungs.


<img  src="https://drive.google.com/uc?id=1QyT6dlq-Ikn1JWKg13c-Ybobk7M4ZLva">





# Obtaining and Scrubbing
<details>
  <summary>Click to read about getting and cleaning the data! </summary>
  
  ## Obtaining
  * We have gathered the data from https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia
     
     
  ## Scrubbing
  * We have used several different methods to clean the data:
      1. Missing data:
          * There was plenty of missing data in this dataset;
          * Meaning that there were many Pneumonia x-rays and almost 1/3 the amount of normal x-rays
      2. Dealing with Missing Data
        * In order to combat the missing data; we created additional random images of the normal xrays that were augmented.
        Each randomly selected images was altered into 20 different images with different zoom, shear, rotation, flips and etc. 
      4. Dataset:
          * Once the training data was balanced we were created dataframes for easy readibility


<img  src="https://drive.google.com/uc?id=1jqChtIUCcGFLTPwoE2A2WG5oi520Lb3v">


</details>  


# Explore
<details>
  <summary>Click to read about exploration of the data! </summary>
  
  ## Exploring
  * While exploring the data, there are some extremely difficult differences between the normal and pneumonia x-rays that would be hard to see
  * To get a better understanding of the different images of the xrays, we opened a few of each of the normal and pneumonia x-rays.
  
Normal
  <img style="float: left;" src="https://drive.google.com/uc?id=1UJmM4bXrfxVIXlo1htkAOFqAhgTUjHdt" >

Pneumonia
  <img style="float: left;" src="https://drive.google.com/uc?id=1C078gPhXNM7G-L7-yU3j2WYB_D3Mp0LK" >
  
  
  
  <p>
    
  For a better visualization of the differnt x-rays (the augmented ones and the original ones), we can look at the below graphs that show a variety of each of the targets

  Normal
  <img style="float: left;" src="https://drive.google.com/uc?id=1UBfxI6QUzpKtAyDwmS74ReXidUZEef_O" >
   


   Pneumonia
   <img style="float: left;" src="https://drive.google.com/uc?id=10YVEs7lESRiCjJHNAsWCbzFkqNl1t86e" >




   As you can see, the augmented images are also present in our normal x-rays. These images allow the model to train equally and intensively on the variety of the normal x-rays with the pnemonia ones.
   </p>
  
     
        
        
</details>




# Model
<details>
  <summary>Click to read about modeling the data! </summary>
  
  ## Modeling
  To model our data effectively; we created a image classifier with many layers.

   <img style="float: center;" src="https://drive.google.com/uc?id=1C0Ibf3Tc8V0-KOCrhDc1niSvJV5cyZK8" >


  * Conv2D 

    * Scans the image and takes each pixel value in a 3x3 (or 4x4, depends on setting) part and multiplies it by a certain weight, adds the numbers and uses that number as the value of the output image of that pixel
    * Depending on the weights, the output image can be blurred, brighter, darker, etc. (basicallu, slight photoshop)

  * MaxPooling2
    * Resizes the output image
    * Takes 2x2 area of a image and chooses the max value in each area
    * Shrinks the image by a factor of two
    * After shrinking usually the images are used for additional filters (Conv2D) in order to train on smaller scales to find more patterns
  
  * Flatten
    * Because we will be using Dense next, we need to use Flatten to reduce the number of dimensions to one dimension
  
  * Dense
    * Dense layers are hidden layers that use different acitvation functions to find the weights of each parameter of the image in order to appropriately learn the images

  * Dropout
    * Usually set to 40%, which means that 40% of the parameters that go into the Dropout are set to zero,
    * This helps the model not overfit

This leads us to having 823,000 differnt parameters that our model is using and going throught in order to train on the images.
  

</details>  
  



# Interpert
<details>
  <summary>Click to read about interperting our results! </summary>
  
  ## Interpreting the results
  * The way to interpret the results, is by reviewing the confusion matrices and classification report and the accuracy and loss of the models.. 



<img style="float: left;" src="https://drive.google.com/uc?id=1cOz9oe9N0vCfpvacObvwQMIExrOIrm4r" >
  * The accuracy plots show the accuracy of the model as it is training. It shows the accuracy for the training data for every epoch, as well as the accuracy during the validation steps (which is the test data)
  

  * The loss plots show the los of the model as it is training. It shows the loss for the training data for every epoch, as well as the loss during the validation steps (which is the test data)
  <img style="float: left;" src="https://drive.google.com/uc?id=1-QGPyNwwubHz8UAmyNnaNn7lp5QfIe7P" >



  * The confusion matrices tells us how well the model performed on the test data by showing us the results of the classification. It shows the number of correct and the number of incorrect classifications
  <img style="float: left;" src="https://drive.google.com/uc?id=1uBVhuLttDoT6xEFvs3v_foNuSAxGZl0y" >
    
    
    * As you can see there the diagonal boxes (from left to right) show the true positive predictions (meaning that the model predicted them and it was correct).
    * As shown, there are more x-rays that are predicted as pneumonia instead of normal. 
    * This is benefical because in regards to the cost and the integrity of this problem, it is better for the model to predict pnemonia for patients to get more test, in order to minimize the loss of life or health





</details>  



# Future Work
<details>
  <summary> Click to future work for analysis! </summary>
  
  ## Future work for Pneumonia X-Rays
  
  * Obtain more normal x-rays  in order for the models to train better and become more accurate.
  * Create deeper models with more layer that can handle learning for longer periods of time and be more accurate

</details>




# Final Project Submission

* Student name: Alisa Radjabova
* Student pace: Full Time
* Scheduled project review date/time: 
* Instructor name: Rafael
* Blog post URL: 
* Presentation: 
* Video : 


