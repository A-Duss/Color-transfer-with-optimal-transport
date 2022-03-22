# Color-transfer-with-optimal-transport
### Antoine DUSSOLLE & Paul NANTAS

As part of the computational imaging course at IMT Atlantique, we implemented the algorithm of the paper *Adaptive Color Transfer With Relaxed Optimal Transport*. The aim of this algorithm is to perform color transfer between images using optimal transport techniques. 
Given two input images, color transfer algorithms impose the color palette of the second image onto the geometry of the first one. 

***Basically, the problem is to find a new image w whose geometry is as close as possible to the source image u and whose color distribution is close to the one of the exemplar image v.***

We can divide this algorithm in three main parts:  
1. **SuperPixel segmentation** : The first step is to segment an image into superpixels. We operate the superpixel segmentation with a given number of clusters on the input and the color-palette images. It allows to keep a more local information about color in images.  

2. **Optimal transport** : Once the image is segmented into superpixels, the next step is to find the best matching between the clusters X of image u and the clusters Y of image v. Here comes the optimal transport techniques and more particularly the relaxed weighted optimal transport mentionned in the article.

3. **Image synthesis and post processing**: This part of the process is made for recovering the sharp details of the input image lost in the process.