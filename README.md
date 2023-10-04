# Demo Code for "Talking Head Anime from a Single Image 2: More Expressive"

两种模式：

  * `manual_poser` 通过GUI操纵二次元角色的面部表情和头部旋转。有两种形式：GUI 和 Jupyter。
  * `ifacialmocap_puppeteer` IOS面捕。

## Try the Manual Poser on Google Colab

在Colab运行[地址](https://colab.research.google.com/github/pkhungurn/talking-head-anime-2-demo/blob/master/colab.ipynb) 

    
## 硬件要求

RTX 2080/3080/Titan/...

## 依赖包

  * Python >= 3.8
  * PyTorch >= 1.7.1 with CUDA support
  * SciPY >= 1.6.0
  * wxPython >= 4.1.1
  * Matplotlib >= 3.3.4


使用Jupyter notebook 运行`manual_poser`, 还需要:

  * Jupyter Notebook >= 6.2.0
  * IPyWidgets >= 7.6.3



### 使用Anaconda构建环境

使用下面的命令，一键生成所需环境`talking-head-anime-2-demo`

```
conda env create -f environment.yml
```

## 模型下载

下载权重文件[this Dropbox link](https://www.dropbox.com/s/tsl04y5wvg73ij4/talking-head-anime-2-model.zip?dl=0) 

目录结构如下所示

```
+ data
  + illust
    - waifu_00.png
    - waifu_01.png
    - waifu_02.png
    - waifu_03.png
    - waifu_04.png
    - waifu_05.png
    - waifu_06.png
    - waifu_06_buggy.png
  - combiner.pt
  - eyebrow_decomposer.pt
  - eyebrow_morphing_combiner.pt
  - face_morpher.pt
  - two_algo_face_rotator.pt
```



## Running the `manual_poser` Desktop Application

```
> python tha2/app/manual_poser.py
```


## Running the `manual_poser` Jupyter Notebook

`tha2.ipynb`

## 图片要求

图片应满足以下要求

  * 有透明通道
  * 只有一个角色
  * 角色必须直视正前方
  * 角色头部大概在128x128的框内
  * 非角色相关的区域，全部为透明像素
  * 图片大小256x256
  
![图片示意图](docs/image_specification.png "Image specification.")
