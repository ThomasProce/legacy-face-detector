# Face Detection Using Legacy Methods

#### Face Detection with HOG Features, Sliding Window, and Pyramid Image

![Example](https://i.ibb.co/6g6b64q/bounding-boxes-without-suppression.png)
![Example](https://i.ibb.co/HXdN1kG/bounding-boxes-after-suppression.png)
![Example](https://i.ibb.co/s9ShXNd/with-full-bounding-boxes.png)
![Example](https://i.ibb.co/FbVqzyC/with-suppression.png)
### Project Description

This Python project focuses on implementing a face detection system using classical computer vision techniques without relying on neural networks or the OpenCV library. Instead, it leverages Histogram of Oriented Gradients (HOG) features, an image pyramid, and sliding window methodology to identify faces within images.

### Key Features

Key Features:

1.  **HOG Features**: The project extracts HOG features from input images, a technique widely employed in object detection tasks. These features capture the local shape and texture information necessary for identifying faces in various scales and orientations.
    
2.  **Image Pyramid**: An image pyramid is constructed by creating a set of scaled-down versions of the input image. This pyramid allows the algorithm to detect faces at different scales, ensuring robustness against variations in face size within the image.
    
3.  **Sliding Window**: The sliding window technique systematically scans the image using a window of fixed size, moving it across the image in both the horizontal and vertical directions. At each position, the HOG features are computed, and a classifier is applied to determine if a face is present within the window.
    
4.  **Non-Maximum Suppression**: To eliminate duplicate detections and improve precision, non-maximum suppression is applied to the bounding boxes obtained from the sliding window approach.
    
5.  **Parameters tuning**: The pipeline encompasses various parameters that can be adjusted to achieve different results based on the input images. For instance, parameters such as the probability threshold, overlap threshold, scale factor, or downscaling can be modified to improve or worsen the outcome, depending on the characteristics of the input image.
    
6.  **Results Visualization**: Detected faces are highlighted in the input image, making it easy for users to visualize the performance of the face detection algorithm.


### Installation

To get started, simply clone this repository to your local machine and run the Jupyter Notebook file.

```bash
git clone https://github.com/ThomasProce/legacy-face-detector.git
cd legacy-face-detector
open face_detector.ipynb
```
### Drawbacks of this kind of implementation

While implementing face detection using legacy methods like HOG features, image pyramids, and sliding windows in Python can be instructive and suitable for certain scenarios, it has several drawbacks compared to modern deep learning-based approaches and libraries like OpenCV. Some of the notable drawbacks include:

1.  **Limited Robustness**: Legacy methods may struggle with detecting faces under challenging conditions, such as extreme lighting variations, occlusions, or non-frontal face orientations. Deep learning-based approaches are generally more robust in handling these scenarios.
    
2.  **Sensitivity to Hyperparameters**: Tuning hyperparameters, such as the window size, overlap, and HOG parameters, can be challenging and may require extensive experimentation to achieve satisfactory results across different datasets and environments.
    
3.  **Slower Execution Speed**: Legacy methods can be significantly slower than deep learning-based approaches, especially when processing high-resolution images or video streams in real-time. This can limit their applicability in time-critical applications.
    
4.  **High False Positive Rate**: The sliding window approach may generate a large number of false positives, as it evaluates numerous image regions that do not contain faces. Post-processing techniques like non-maximum suppression can help, but they may not completely eliminate false positives.
    
5.  **Dependency on Handcrafted Features**: HOG features are handcrafted and may not capture complex patterns and variations in facial appearance as effectively as deep learning-based features, which learn representations from data.
    
6.  **Limited Generalization**: Legacy methods might not generalize well to different datasets or demographic groups due to their reliance on fixed features and heuristics. They may require retraining or extensive customization for specific use cases.
    
7.  **Difficulty in Handling Multiscale and Multiorientation**: While image pyramids help address scale variations, handling multiple face orientations (e.g., profile faces) can be challenging and may require additional techniques or detectors.
    
8.  **Maintenance and Portability**: Maintaining and extending a custom face detection implementation can be more cumbersome than using a widely adopted library like OpenCV, which benefits from community contributions and updates.
    
9.  **Lack of Adaptability**: Unlike deep learning models, which can be fine-tuned or retrained for specific tasks, legacy methods may lack adaptability and may not perform optimally on novel face detection challenges.
    
### *References:*

1. [TensorFlow Object Detection API Tutorial - Training](https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/latest/training.html)

2. [Bayesian Quest part I](https://bayesianquest.com/2022/04/07/build-you-computer-vision-application-part-ii-data-preperation-and-annotation/)

3. [Bayesian quest part II](https://bayesianquest.com/2022/04/20/build-you-computer-vision-application-part-iii-pothole-detector-from-scratch-using-legacy-methods-image-pyramids-and-sliding-window/)


*In summary, while legacy face detection methods can be educational and suitable for specific applications where deep learning may not be an option, they come with limitations in terms of accuracy, speed, and adaptability, making them less desirable for many modern computer vision tasks.*
