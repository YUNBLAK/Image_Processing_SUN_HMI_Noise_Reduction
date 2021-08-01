# Image_Processing_Noise_Reduction
## by YUNBLAK 
### Image Processing for Noise Reduction

[**IMAGES ARE FROM NASA**]

When analyzing our image, the noise present in the image can cause problems in finding the desired image part or characteristics. Therefore, we implemented a method to eliminate the noise of images before finding the desired characteristics in the images.

## Original Image
![NOISED002](https://user-images.githubusercontent.com/87653966/127761712-1f45f792-ea9e-403e-9fca-404a0deec995.png)

In this original image, when we create an algorithm to find a black spot, we detect the sunspots and the noise simultaneously due to the noise. To prevent such problems in advance, we de-noise the images, making them easier to detect sunspots.

## Image with Noise Reduction
![NOISED001](https://user-images.githubusercontent.com/87653966/127761713-ad1a3e7b-64da-43cf-b763-baed94c5547a.png)

#### This is a main noise reduction method in Python

    def noise_cancelling(img, a, b, c, d):
      cancelled_img = cv2.fastNlMeansDenoisingColored(img, None, a, b, c, d)
      return cancelled_img
    
    # a : The factor that determines the filter strength. Higher a values better eliminate noise 
    #     but also eliminate non-noise pixels (10 is appropriate)
    # b : Same as a, but only used for color images (usually equal to a)
    # c : templateWindowSize : Must be an odd value (5 is recommended)
    # d : searchWindowSize : Must be an odd value (21 is recommended)

#### 
