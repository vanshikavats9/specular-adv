# specular-adversarial

We introduce specular highlight as a natural adversary and examine how deep neural network classifiers can get affected by them, resulting in a reduction in their prediction performance.

Paper

We also provide two datasets, ImageNet-AH and ImageNet-PT, depicting:

- ImageNet-AH: Artificially generated augmentations of Gaussian specular highlights [[Download]](https://drive.google.com/drive/folders/1xEwymaOZnKzOiBqqdBrurMTNIgP5ZYuk?usp=sharing)
- ImageNet-PT: Actual specular highlights on the printed images [[Download]](https://drive.google.com/drive/folders/14BqEKZYOWqP7Jsi4O1W18A3qucUG80oh?usp=sharing)

![teaser](assets/teaser_jeep.pdf)

ImageNet Augmented Highlight (ImageNet-AH) is a collection of specular highlighted images (using augmentation) with specular highlights at various locations and intensities. This specially curated dataset contains those specular augmentations that fooled the classifiers into making a wrong decision but had their original images correctly classified. This will help us to claim that when we put a specular highlight on the image, the models change their decision towards a misclassification. The dataset is curated in such a way that we get a pool of failed images, mispredicted by any of the pre-trained classifiers considered in this study. The meta data contains each model prediction, with the current class, the intensity of specular highlight, image name, incorrect predicted class code, and the incorrect predicted class name.

The image name is saved as ```(<ImageNum>_<Class>_<ClassName>_<Intensity>_<Position>)```. Here, the position (P) number varies from 1-100. Since the image is divided into 5x5 grid (25 unique positions), P represents one of those 25 positions per intensity value (I(sigma) = 10, 20, 30, 40). The counting is row-first, and hence the total P values are ```P * I(sigma) = 25*4 = 100```. 

