# Cartoonify an Image with OpenCV in Python.

Here, I aim to transform images into its cartoon. Yes, I will make cartoon of the images. Thus, let's build a python application that will transform an image into its cartoon using OpenCV.

# Step 1: Importing the required modules.
Import the following modules:

1. CV2: Imported to use OpenCV for image processing </br>
2. easygui: Imported to open a file box. It allows us to select any file from our system.</br>
3. Numpy: Images are stored and processed as numbers. These are taken as arrays. We use NumPy to deal with arrays.</br>
4. Imageio: Used to read the file which is chosen by file box using a path.</br>
5. Matplotlib: This library is used for visualization and plotting. Thus, it is imported to form the plot of images.</br>
6. OS: For OS interaction. Here, to read the path and save images to that path.</br>

# Step 2: Building a File Box to choose a particular file.
In this step, build the main window of application, where the buttons, labels, and images will reside. Also give it a title by title() function.

Explanation:
fileopenbox() is the method in easyGUI module which returns the path of the chosen file as a string. It opens the file box, i.e the pop-up box to choose the file from the device, which opens every time while running the code.
NOTE: Now, all the operation will be done on the button click, thus all the below steps are the part of function cartoonify (ImagePath)

# Step 3: How to store an Image?
For a computer, everything is just numbers. Thus, convert an image into a numpy array.</br>
<ul>
<li> .imread() is a method in cv2 which is used to store images in the form of numbers. This helps to perform operations according to needs. </li>
<li> The image is read as a numpy array, in which cell values depict R, G, and B values of a pixel. Resize the image after each transformation to display all the images on a similar scale at last.</li>
<li> To convert an image to a cartoon, multiple transformations are done. Firstly, an image is converted to a Grayscale image.</li>
<li> Then, the Grayscale image is smoothened, and then try to extract the edges in the image.</li>
<li> Finally, form a color image and mask it with edges. This creates a beautiful cartoon image with edges and lightened color of the original image.</li>
</ul>

# Step 4: Transforming an image to grayscale
cvtColor(image, flag) is a method in cv2 which is used to transform an image into the colour-space mentioned as ‘flag’. Here, first step is to convert the image into grayscale. Thus, use the BGR2GRAY flag. This returns the image in grayscale. A grayscale image is stored as grayScaleImage.</br>

After each transformation, resize the resultant image using the resize() method in cv2 and display it using imshow() method. This is done to get more clear insights into every single transformation step.

# Step 5: Smoothening a grayscale image
To smoothen an image, simply apply a blur effect. This is done using medianBlur() function. Here, the center pixel is assigned a mean value of all the pixels which fall under the kernel. In turn, creating a blur effect.

# Step 6: Retrieving the edges of an image
Cartoon effect has two specialties: Highlighted Edges and Smooth colors.</br>
In this step, For Highlighting edges try to retrieve the edges and highlight them. This is attained by the adaptive thresholding technique.</br>

# Step 7: Preparing a Mask Image
Now, prepare a lightened color image to mask with edges at the end to produce a cartoon image. Use bilateralFilter which removes the noise. It can be taken as smoothening of an image to an extent.</br>

The third parameter is the diameter of the pixel neighborhood, i.e, the number of pixels around a certain pixel which will determine its value. The fourth and Fifth parameter defines signmaColor and sigmaSpace. These parameters are used to give a sigma effect, i.e make an image look vicious and like water paint, removing the roughness in colors. It’s similar to BEAUTIFY or AI effect in cameras of modern mobile phones.

# Step 8: Giving a Cartoon Effect
let’s combine the two specialties. This will be done using MASKING. Perform bitwise and on two images to mask them.

# Step 9: Plotting all the transitions together
To plot all the images, first make a list of all the images. The list here is named “images” and contains all the resized images. Now, create axes in a plot and display one-one images in each block on the axis using imshow() method. plt.show() plots the whole plot at once after we plot on each subplot. Figure_1.png showas all the transitions.

# Step 10: Functionally of save button
Here, the idea is to save the resultant image. For this, we take the old path, and just change the tail (name of the old file) to a new name and store the cartoonified image with a new name in the same folder by appending the new name to the head part of the file.

# Step 11: Make the main window, Make the Cartoonify button in the main window and Make a Save button in the main window.

# Step 12: Main function to build the tkinter window
Use top.mainloop() for building tkinter window.
