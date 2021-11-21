# The Sign Of Lore

## Problem Scenario

`American Sign Language (ASL)` substantially facilitates communication in the deaf community. However, there are only ~250,000-500,000 speakers which significantly limits the number of people that they can easily communicate with. The alternative of written communication is cumbersome, impersonal and even impractical when an emergency occurs.

## Our Approach 

 In order to
diminish this obstacle and to enable dynamic communication, we present an ASL recognition system that uses Convolutional Neural Networks (CNN) in real time to translate data of a user’s ASL signs into text. Our problem consists of three tasks to be done :

```diff
- Obtaining data of the user signing (input)
+ Classifying each frame in the data to a letter
! Reconstructing and displaying the most likely word from classification scores (output)
# text in gray
@@ text in purple (and bold)@@
```
## Potential Client

## Project Workflow
## Data Description

![#f03c15](https://via.placeholder.com/15/f03c15/000000?text=+) The dataset format is patterned to match closely with the classic MNIST. Each training and test case represents a >label (0-25) as a one-to-one map for each alphabetic letter A-Z (and no cases for 9=J or 25=Z because of gesture motions). 

>The training data (27,455 cases) and test data (7172 cases) are approximately half the size of the standard MNIST but otherwise similar with a header row of label, >pixel1,pixel2….pixel784 which represent a single 28x28 pixel image with grayscale values between 0-255. 

The original hand gesture image data represented multiple users repeating the gesture against different backgrounds.

The Sign Language MNIST data came from greatly extending the small number (1704) of the color images included as not cropped around the hand region of interest. To create new data, an image pipeline was used based on ImageMagick and included cropping to hands-only, gray-scaling, resizing, and then creating at least 50+ variations to enlarge the quantity. 

The modification and expansion strategy was filters ('Mitchell', 'Robidoux', 'Catrom', 'Spline', 'Hermite'), along with 5% random pixelation, +/- 15% brightness/contrast, and finally 3 degrees rotation. Because of the tiny size of the images, these modifications effectively alter the resolution and class separation in interesting, controllable ways.
