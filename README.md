# Forest Cover Change Detection and Prediction over Pakistani Areas
<p align='center'>
    <!-- <img src='http://informationcommunicationtechnology.com/wp-content/uploads/2018/06/Forest-Wallpaper.jpg' width="800" height="500"/> -->
    <img src='https://www.google.de/url?sa=i&rct=j&q=&esrc=s&source=images&cd=&cad=rja&uact=8&ved=2ahUKEwjq5cqO5qjdAhXEjKQKHdQ-CiIQjRx6BAgBEAU&url=https%3A%2F%2Fwww.pri.org%2Fstories%2F2016-12-30%2Findonesia-s-rapidly-disappearing-forests-four-charts&psig=AOvVaw2EDpOiduHiqsjp7TeiMzym&ust=1536406412309645' width="400" height="400"/>
</p>

The aim of this project is to use Sentinel and Landsat imagery in order to perform forest cover change detection in Pakistan. The first step is to segment an image from our AOI and then do the same for a whole temporal series of images and finally compare them to see what changes occured in forest areas. We also intend to predict forestation change trend in Pakistan.                                                                                      

## Getting Started

All of the models in this repo are written with [pytorch](https://github.com/pytorch/pytorch).

### Dependencies

You will need the following modules to get the code running

* [pytorch](https://github.com/pytorch/pytorch)
* [torchsummary](https://github.com/sksq96/pytorch-summary)
* [torchviz](https://github.com/szagoruyko/pytorchviz)
* [gdal](https://pypi.org/project/GDAL/)
* [imgaug](https://github.com/aleju/imgaug)


## Results

### Image Segmentation on ISPRS data set using UNet architecture.
**Unet Architecture** 
<p align='center'> 
    <img src="results/unet-architecture.png">
</p>

**[Vaihingen Dataset](http://www2.isprs.org/commissions/comm3/wg4/semantic-labeling.html) Segmentation after downsampling**
<p align='center'> 
    <img src="results/downsampled_seg_result.png">
</p>

### Patch-wise classification of Sentinel-2 Satellite Images.
We used the [Eurosat](https://arxiv.org/pdf/1709.00029.pdf) data set and a [Resnet-50](https://pytorch.org/docs/stable/torchvision/models.html#torchvision.models.resnet50) model for classifying 64*64 patches of image.
Here is our Confusion Matrix on the test set
<p align="center"> 
    <img src="results/resnet_cm.png" width="500" height="500"/>
</p>

* The following images show our results one different landscapes. It should be noted that these images were not a part of the training or test set. They were downloaded separately from [scihub](https://scihub.copernicus.eu) and [earthexplorer](http://earthexplorer.usgs.gov) for inference.  

**`Change Detection on a series of Sentinel Images from German Landscapes (2016-2018)`**
<p align='center'> 
    <img src="results/10_10.gif"/>
    <img src="results/20_20.gif"/>
</p>

**`Same result but color coded in full resolution`**
<p align='center'> 
    <img src="results/rgb_color_coded_segmentation/seg.gif"/>
</p>


- **Germany**
<p align="center"> 
    <img src="results/german_patchwise_1.png"/>
    <img src="results/german_patchwise_2.png"/>
</p>

- **Pakistan (Peshawar Region)**
<p align="center"> 
    <img src="results/peshawar_patchwise_1.png"/>
    <img src="results/peshawar_patchwise_2.png"/>
</p>

- **Pakistan (Muzaffarabad Region)**
<p align="center"> 
    <img src="results/muzaffarabad_patchwise_1.png"/>
    <img src="results/muzaffarabad_patchwise_2.png"/>
</p>

## Authors

* **Annus Zulfiqar**

See also the list of [contributors](https://github.com/annusgit/ForestCoverChange/graphs/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE) file for details

## Acknowledgments

* [Sentinel](https://scihub.copernicus.eu/) program for providing complete coverage of Earth for free
* [Eurosat](https://arxiv.org/pdf/1709.00029.pdf) for providing a labeled dataset
* [Pytorch Forum](http://discuss.pytorch.org/) for providing valuable help when needed







