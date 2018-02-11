![Oryx](http://teleported.in/post_imgs/09-arabian-Oryx-detection.png)

    Recently I spent 4 months at [Flytbase](https://flytbase.com/) on an interesting problem: detection and counting of Oryxes, an endangered animal in the middle east, in very high resolution aerial images.

    Using high resolution aerial images to train computer vision models poses unique challenges:

    * Lack of sufficient training data: There are plenty of open training datasets out there, but almost all of them have images taken from human eye level. What makes aerial images unique is their top-down view of the objects. Moreover, for custom object detection, customers don’t often have enough images to train the model on, wherein we have to make do with limited set of images.

    * Very high resolution of the images: Computer vision models can process images of limited resolution at a time. For high-resolution images, we need to crop the images into sizable chunks and run inference on them one at a time. This can lead to double counting or misses.

    * Shallow features of objects: When looked down from the top, objects can have very generic shapes which a) can be hard to detect and b) can appear to be similar to other objects.

    These challenges were mitigated via various techniques, including data augmentation, cropping with different offsets for hi-res images, and training models on similar looking objects for better differentiation.

    I built a pipeline using Tensorflow's Object Detection API and used Faster-RCNN for the purpose of detection.

    This also marked the launch of Flytbase's AI platform, their capabilities to provide intelligent applications on top of their drone platform.

    You can read more about this project via my writings here:

    * [Press release](https://www.suasnews.com/2017/10/flytbase-releases-ai-platform-drones/)
    * [Blog post 1](https://blogs.flytbase.com/ai-drones/)
    * [Blog post 2](https://blogs.flytbase.com/arabian-oryx-detection-counting/)


