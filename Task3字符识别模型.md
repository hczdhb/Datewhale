# CNN卷积神经网络
卷积积神经网络（简称CNN）是一类特殊的人工神经网络，是深度学习中重要的一个分支。CNN在很多领域都表现优异，精度和速度比传统计算学习算法高很多。特别是在计算机视觉领域，CNN是解决图像分类、图像检索、物体检测和语义分割的主流模型。CNN每一层由众多的卷积核组成，每个卷积核对输入的像素进行卷积操作，得到下一次的输入。随着网络层的增加卷积核会逐渐扩大感受野，并缩减图像的尺寸。

![卷积](https://user-images.githubusercontent.com/55572398/82893325-6ad38280-9f83-11ea-83f9-708cd33bcccd.png)

CNN是一种层次模型，输入的是原始的像素数据。CNN通过卷积（convolution）、池化（pooling）、非线性激活函数（non-linear activation function）和全连接层（fully connected layer）构成。

<img width="1151" alt="截屏2020-05-26 下午7 08 53" src="https://user-images.githubusercontent.com/55572398/82894016-825f3b00-9f84-11ea-92e4-d3dfeaceaf65.png">

可以卷积核对应于一个矩阵，其中的参数都是经过训练（学习）出来的，将卷积核中的值和图片中的像素值做点积，就会得到新的矩阵，可以把新的矩阵理解为卷积核提取的图片的特征图（feature map），如下图所示


<img width="1036" alt="截屏2020-05-26 下午7 16 13" src="https://user-images.githubusercontent.com/55572398/82894619-6b6d1880-9f85-11ea-8106-abcbe627dc94.png">




