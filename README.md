# CycleCoopNet

Using Tensorflow to learn image-to-image translation **without** input-output pairs.


CycleCoopNet method is proposed by Chien-Hao Weng in 
[CycleCoopNet: Image-to-Image Translation with Cooperative Learning Networks](https://github.com/howarder3/Cycle_CoopNet). 


## Prepare environment

> In our experient environment, we use windows 10 with NVIDIA GTX1060 6GB GPU, Intel i5-7400 CPU. 

### install CUDA 9.0

For NVIDIA GPU users, we install CUDA 9.0 for GPU device driver. Your can find it on CUDA Toolkit downloads website. 

- Download link:
https://developer.nvidia.com/cuda-90-download-archive

> We are NOT sure the newest version of CUDA can work. 
 
### install cuDNN 7.0

cuDNN is part of the NVIDIA Deep Learning SDK. We can install it in the cuDNN developer website. Remember to choose the version that matches your Tensorflow version.

- Download link:
https://developer.nvidia.com/rdp/cudnn-download

> We are also NOT sure the newest version of cuDNN can work. 



### create new Anaconda environment

Here we use Anaconda to help us manage python environment.
You can download it on [Anaconda website](https://www.anaconda.com/).

 
Use Anaconda to create a new python environment, and install all python packages below.

```
conda create -n [your-environment-name] python=3.6.3
conda activate [your-environment-name]
```

> Or you can use Anaconda GUI to create your own python environment:
> 
> ![alt text](https://github.com/howarder3/CycleCoopNet/blob/master/anaconda_GUI.png?raw=true)

### install python Packages
- tensorflow-gpu 1.13.1
- numpy 1.15.4
- scipy 1.1.0
- pillow 5.3.0
- pandas 0.23.4



## Getting Started

### Prepare the model

- Clone this repository:
```
git clone https://github.com/howarder3/CycleCoopNet
```


### Download training dataset

- edges2handbags dataset
```bash
bash ./download_dataset_bag.sh	
```

- vangogh2photo dataset
```bash
bash ./download_dataset_vangogh.sh
```

### Start Training a model

Training a model: (e.g. edges2handbags datasets)
```bash
python main.py --dataset_name=edges2handbags
```

## Testing

Put the picture your want to test in the "test_datasets" folder, you can find these results in the "sample" folder.
(After you start the training, this folder will auto create by our program.)

> The testing pictures will NOT affect the model training, that is, these pictures will NOT change the parameters of the model.



## Experiment Results Sample

- Sketches -> Bags <br>

sketch:
![alt text](https://github.com/howarder3/CycleCoopNet/blob/master/sample_results/test_bag_1.jpg?raw=true)


Our result:
![alt text](https://github.com/howarder3/CycleCoopNet/blob/master/sample_results/result_bag_1.jpg?raw=true)


sketch:
![alt text](https://github.com/howarder3/CycleCoopNet/blob/master/sample_results/test_bag_2.jpg?raw=true)


Our result:
![alt text](https://github.com/howarder3/CycleCoopNet/blob/master/sample_results/result_bag_2.jpg?raw=true)

- Photos -> VanGogh-style picture <br>

Photos:
![alt text](https://github.com/howarder3/CycleCoopNet/blob/master/sample_results/test_photo_1.jpg?raw=true)


Our result:
![alt text](https://github.com/howarder3/CycleCoopNet/blob/master/sample_results/result_photo_1.png?raw=true)



Photos:
![alt text](https://github.com/howarder3/CycleCoopNet/blob/master/sample_results/test_photo_2.jpg?raw=true)


Our result:
![alt text](https://github.com/howarder3/CycleCoopNet/blob/master/sample_results/result_photo_2.png?raw=true)


- VanGogh picture -> real style <br>

VanGogh picture:
![alt text](https://github.com/howarder3/CycleCoopNet/blob/master/sample_results/test_vangogh_1.png?raw=true)


Our result:
![alt text](https://github.com/howarder3/CycleCoopNet/blob/master/sample_results/result_vangogh_1.png?raw=true)



VanGogh picture:
![alt text](https://github.com/howarder3/CycleCoopNet/blob/master/sample_results/test_vangogh_2.png?raw=true)


Our result:
![alt text](https://github.com/howarder3/CycleCoopNet/blob/master/sample_results/result_vangogh_2.png?raw=true)



## Some of our analysis tools

- Generating loss chart of pix2pix, https://github.com/howarder3/analysis_pix2pix_by_yenchenlin
> Original work: https://github.com/howarder3/analysis_pix2pix_by_yenchenlin

- Generating loss chart of CycleGAN, https://github.com/howarder3/analysis_CycleGAN_by_xhujoy
> Original work: https://github.com/xhujoy/CycleGAN-tensorflow

- Analysing of generated pictures, https://github.com/howarder3/analysis_generated_pictures


## Reference
Github:

- The torch implementation of CycleGAN, 
https://github.com/junyanz/CycleGAN
- The tensorflow implementation of CycleGAN, 
https://github.com/xhujoy/CycleGAN-tensorflow
- The tensorflow implementation of pix2pix, 
https://github.com/yenchenlin/pix2pix-tensorflow

Websites:

- Win10 安裝 TensorFlow-gpu & Keras
https://medium.com/@WhoYoung99/2018最新win10安裝tensorflow-gpu-keras-8b3f8652509a
- Tensorflow-gpu在windows10上的安裝(anaconda)
https://hk.saowen.com/a/b18554aeda7d3f5a43d7dafdbd9b0a9f1bda2b9b0406d3317c6be836ce717fc3
- python程式
https://github.com/zilongzheng/CoopNets
