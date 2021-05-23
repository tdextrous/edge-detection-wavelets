# Image edge detection with wavelets
This code implements a method from Mallat and Hwang (1992) for detecting edges in images using the wavelet transform modulus maxima method.
As stated in the reference, this method is similar to the Canny edge detection method, but interpreted in the context of the wavelet transform.

The paper outlines a construction of wavelets via a 'smoothing function' and the partial derivatives thereof. Here, the chosen smoothing function was the 
jointly normal 2D zero mean unit variance Gaussian distribution, in part due to its existing applications in edge detection and image processing methods.

The `samples/` directory contains some sample input images and the outputs of the code with certain parameters. The output filenames can be interpreted as follows:
`s${integer}` stands for the exponent of the dyadic scaling factor the algorithm was evaluated at. So `s4` means that the output image was produced
with a scale factor of 2^4. The `t${number}` stands for the final threshold value used to eliminate any remaining noise from the image. So `t015` means that
any final pixel values below 0.15 were removed from the final output image.

To run the code, open the `wtmm.m` file in matlab and change the `img_file_name` value to the relative filepath of your image (preferably in JPEG format). Then after
running the code, a window should pop up allowing you to save the output image. Tweaking the `scale` and `threshold` values in the code allow for a wide range of 
results, and in general the best values for these parameters vary based on the input image.

This code was developed as part of a final project for MATH 414 at Texas A&M University in Spring 2021.

## Example
Input image:

![Input image of man with camera](https://github.com/tdextrous/edge-detection-wavelets/blob/bbd66750ea0ffac18a204c889044f86739dc3915/samples/inputs/man_with_camera_gray.jpeg)

Output image: (Scale-factor 2^4, Threshold value 0.2)

![Output image of man with camera (scale factor 2^4, threshold 0.2)](https://github.com/tdextrous/edge-detection-wavelets/blob/bbd66750ea0ffac18a204c889044f86739dc3915/samples/outputs/man_with_camera_s4_t02.jpg)

## References
 - Mallat, S., & Hwang, W. (1992). Singularity detection and processing with wavelets. IEEE Transactions on Information Theory, 38(2), 617–643. https://doi.org/10.1109/18.119727
