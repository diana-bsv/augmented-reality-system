# Augmented reality system

### Project **Development of an Augmented Reality System** 

This project was done as part of coursework in "Computer Vision nad Image Processing" course at the University of Bologna.

Result of the project is a software system aimed at creating an Augmented Reality (AR) video («output.avi»). The task was solved by applying Frame to Reference (F2R) method.

### Key points of the program are:

- The program automatically extracts the edge points of the book by
finding the edge points of the book mask and applying linear
interpolation to it

- Then it crops the book cover and removes its perspective deformation. It
does the same with the augmented layer and the masks of both objects.

It makes possible to apply any 2D rectangular layer on top of the book.
(We do not need to manually deform the augmented layer to fit the
reference frame)

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp;<img height="400" alt="ar1" src="https://github.com/diana-bsv/augmented-reality-system/assets/127965240/a3fed7e8-5de3-4fd2-bfec-9d50bc3e3dcf">
&nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; <img  height="400" alt="ar2" src="https://github.com/diana-bsv/augmented-reality-system/assets/127965240/64e0f924-82be-455d-8b87-1b4e5dce45aa">

Then the program applies the same algorithm to each frame of the video
- Finds key points in the book cover image and the current frame image
- Describing them
- Looks for the similarities using the FLANN algorithm
- Leaves only «good» matches with the threshold 0.7
- If we have found enough good matches, program finds a homography
between the original book cover image and the book in the current
frame image
- Using that homography we warp the augmented layer and its mask
- We also warp the original image (the reference frame) in order to fit the
colour of augmented layer to the brightness changes of current frame.

Program multiplies colours of each pixel by a coefficient. Which is the ratio
between current and original frames colours. It allows for example to light
reflections to pass through the applied augmented layer.

&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<img width="400" alt="ar3" src="https://github.com/diana-bsv/augmented-reality-system/assets/127965240/412c743b-9d17-4608-b728-ca275a7517be">
&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<img width="400" alt="ar4" src="https://github.com/diana-bsv/augmented-reality-system/assets/127965240/56b1e6a1-e9b2-4d00-b988-e0eb26891582">

### Issues that I faced during the project
Due to lack of sharpness on the edges of the augmented layer the letters on the layer disappear when the significant brightness changes occur. It happens because of the cropping and warping the original augmented layer.

I solved that by applying filtering to the resulting augmented layer.

&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<img width="400" alt="ar5" src="https://github.com/diana-bsv/augmented-reality-system/assets/127965240/9849b848-67d0-4623-b0d0-12e01f92a9a5">
&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<img width="400"  alt="ar6" src="https://github.com/diana-bsv/augmented-reality-system/assets/127965240/b6be09e7-aa39-4346-a2c9-bca05466f67f">


