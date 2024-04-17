# Augmented reality system

Project **Development of an Augmented Reality System** 

This project was done as part of coursework in "Computer Vision nad Image Processing" course at the University of Bologna.

Result of the project is a software system aimed at creating an Augmented Reality (AR) video («output.avi»). The task was solved by applying Frame to Reference (F2R) method.

Key points of the program are:

- The program automatically extracts the edge points of the book by
finding the edge points of the book mask and applying linear
interpolation to it

- Then it crops the book cover and removes its perspective deformation. It
does the same with the augmented layer and the masks of both objects.

It makes possible to apply any 2D rectangular layer on top of the book.
(We do not need to manually deform the augmented layer to fit the
reference frame)

