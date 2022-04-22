# **Morphological operators**

## **Erosion** 

Erosion reduces the shape of the image by eroding the boundaries of region of the foreground pixels. This way areas of the foreground pixels shrinks in size. There are two main inputs of the erosion operator: image and structural element/kernel which helps to identify the level of erosion need to be conducted. The value of the output is the minimum value of all the pixels in the neighboring pixels.

*Algorithm:*
* Read the image
* Define the structuring element/kernel using matrix odd size is convolved with the image
* Then conduct padding of the matrix using numpy.pad() and pad_with which defined the number of values that are padded to the edge of each axis.
* Position the center of the kernel and iteratively let submatrices visit the position of the center value of the kernel.
* If original image and kernel is equal, then replace the pixel value to 1 or 255, unless 0.
* Choose the minimum pixels of all the pixels in the neighboring pixels. Numpy min() is used to find the minimum pixels.


*Results:* Following images are the output of the erosion function.

Image: gun.bmp            
<img width="148" alt="image" src="https://user-images.githubusercontent.com/57295556/164739656-4002aa93-73b8-480b-b17c-b16240056448.png">



Image: palm.bmp

<img width="143" alt="image" src="https://user-images.githubusercontent.com/57295556/164739780-0f011c95-6415-4ee6-9db2-93bd639b5b6a.png">


The eroded results is eroded on 3x3 square matrix and performs erosion of the given gun and palm images. Relative to the given input, image is significantly decreased its thickness and foreground pixels.
____

## **Dilation** 
Dilation adds pixel boundaries of the object to image which expand the size of the image. The number of pixels added depends on the size and shape of the structural element/kernel.

*Algorithm:*
Similar to erosion algorithms, but two main changes:
* If one pixel in kernel is one, then pixel value in original image is also equal to 1.
* Instead of using np.min(), np.max() is used which looks for the maximum pixels in its neighborhood.

Results: Following are the output for dilation. 

Image: gun.bmp    

<img width="185" alt="image" src="https://user-images.githubusercontent.com/57295556/164740451-a33fac28-f54a-4e03-bdea-e2583f41c6ca.png">

Image: palm.bmp

<img width="178" alt="image" src="https://user-images.githubusercontent.com/57295556/164740473-07c138d6-aa51-48dc-aa28-3c2a035d629c.png">

As seen in the results part, using dilation, the size of image is expanded.
___

## **Opening** 

Opening in Morphological operations is used to in order to filter the noise in image. Simply, it’s when dilation after erosion. In math, it can be represented as (AoB) which represents the terms of erosion and dilation. 

Results: After applying eroded image to dilation, following result is achived.

Result after eroding and performing the opening operation for palm image.

<img width="193" alt="image" src="https://user-images.githubusercontent.com/57295556/164740670-9e7f487c-fa42-43c3-9063-83aa5a8ee832.png">

Then image is dilated in order to perform the opening operation which is shown below for gun image.

<img width="177" alt="image" src="https://user-images.githubusercontent.com/57295556/164740706-20b672c6-3d3e-4f28-b2d1-b8f0071e0af9.png">

___

## **Closing** 

Closing is the opposite of the opening operation. Its dilation followed by erosion. 
After the opening operation, closing operation is conducted where first we conduct the dilation and then erosion.

Result: After performing closing, following result is reached.

Image: palm.bmp after closing

<img width="185" alt="image" src="https://user-images.githubusercontent.com/57295556/164740766-e9617645-609b-4d16-8696-cb9628a71f2e.png">

Image: gun.bmp after closing

<img width="185" alt="image" src="https://user-images.githubusercontent.com/57295556/164740778-42249ae3-596a-4b9f-ae23-8f977f2e96df.png">

___
## **Boundary**

Boundary is the difference between the original image eroded image. Here, we first erode the image and then subtract the original image from eroded one. 

Result: Following result is obtained on the gun image on the first left and palm image on the second left. 

Image: palm.bmp after boundary extraction

<img width="201" alt="image" src="https://user-images.githubusercontent.com/57295556/164741751-ba5abe23-48f4-4715-8a89-fc9f4db8c45c.png">

Image: palm.bmp after boundary extraction

<img width="201" alt="image" src="https://user-images.githubusercontent.com/57295556/164741808-c5d5ae03-f15b-4d3a-94d6-dfdb9df1a8e0.png">
 

