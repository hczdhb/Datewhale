# Task2 数据读取与数据扩增

## 学习目标
1. 学习python和pytorch图像读取
2. 学会扩增方法和pytorch读取赛题数据


## 1.图像读取
方法： 用pillow和opencv库读取图像数据

### pillow
Pillow是Python图像处理函式库(PIL）的一个分支。
优点：可以与ipython notebook无缝集成，应用广泛。

| 效果 | 代码 |
| ------------- | ------------- |
|![cat](https://user-images.githubusercontent.com/55572398/82728270-edf59e00-9d21-11ea-95bc-f7802e96a41c.jpg)| <img width="558" alt="截屏2020-05-23 下午6 22 19" src="https://user-images.githubusercontent.com/55572398/82728449-bb987080-9d22-11ea-927b-a0c22bf62364.png">|
|![blur](https://user-images.githubusercontent.com/55572398/82729244-8c84fd80-9d28-11ea-8382-f0075f8dee95.jpg) | <img width="705" alt="截屏2020-05-23 下午7 05 43" src="https://user-images.githubusercontent.com/55572398/82729250-9dce0a00-9d28-11ea-915d-2c862246961b.png"> |
|![thumbnail](https://user-images.githubusercontent.com/55572398/82729528-d40c8900-9d2a-11ea-82de-da430390012a.jpg)  | <img width="477" alt="截屏2020-05-23 下午7 22 10" src="https://user-images.githubusercontent.com/55572398/82729537-e7b7ef80-9d2a-11ea-8711-2137180e7396.png"> |
* 注意点： 有的图片模式可能是其他的 ，如：'p', 'L', 'RGBA' ,需要利用convert方法转换图片的模式，变成mode='RGB',然后才能保存为jepg格式的图片

### OpenCv
| 效果 | 代码 |
| ------------- | ------------- |
| <img width="548" alt="截屏2020-05-23 下午8 31 26" src="https://user-images.githubusercontent.com/55572398/82730711-67968780-9d34-11ea-8cf9-ecbe47b03fbd.png"> |<img width="471" alt="截屏2020-05-23 下午8 40 31" src="https://user-images.githubusercontent.com/55572398/82730936-1ab3b080-9d36-11ea-93b1-48674ea5a594.png"> |
| <img width="528" alt="截屏2020-05-23 下午8 06 15" src="https://user-images.githubusercontent.com/55572398/82730712-68c7b480-9d34-11ea-889c-a1b54aa58693.png"> | <img width="343" alt="截屏2020-05-23 下午8 41 50" src="https://user-images.githubusercontent.com/55572398/82730940-20a99180-9d36-11ea-8ca4-29a8d38dbb9a.png"> |
| <img width="534" alt="截屏2020-05-23 下午8 28 28" src="https://user-images.githubusercontent.com/55572398/82730713-69f8e180-9d34-11ea-9c34-0d117ad6b8d8.png">|<img width="313" alt="截屏2020-05-23 下午8 41 14" src="https://user-images.githubusercontent.com/55572398/82730943-22735500-9d36-11ea-9a0a-e416d5a557bf.png">

## 数据扩增方法
当你训练一个机器学习mode时候，你真正做的就是调参以便它能将输入（比如图片）映射到输出（比如标签）。我们优化目标是追求我们模型损失较低的最佳点，当参数以正确的方式调整时就会发生这种情况。
最领先的神经网络有着数百万的参数！
显然，如果你有很多参数，你需要给你的模型足够比例的样本。同样，你需要的参数的个数与你任务的复杂度成比例。

- 有哪些数据扩增方法
数据扩增方法有很多：从颜色空间、尺度空间到样本空间，同时根据不同任务数据扩增都有相应的区别。
对于图像分类，数据扩增一般不会改变标签；对于物体检测，数据扩增会改变物体坐标位置；对于图像分割，数据扩增会改变像素标签。
在常见的数据扩增方法中，一般会从图像颜色、尺寸、形态、空间和像素等角度进行变换。当然不同的数据扩增方法可以自由进行组合，得到更加丰富的数据扩增方法。

以torchvision为例，常见的数据扩增方法包括：

- transforms.CenterCrop 对图片中心进行裁剪
- transforms.ColorJitter 对图像颜色的对比度、饱和度和零度进行变换
- transforms.FiveCrop 对图像四个角和中心进行裁剪得到五分图像
- transforms.Grayscale 对图像进行灰度变换
- transforms.Pad 使用固定值进行像素填充
- transforms.RandomAffine 随机仿射变换
- transforms.RandomCrop 随机区域裁剪
- transforms.RandomHorizontalFlip 随机水平翻转
- transforms.RandomRotation 随机旋转
- transforms.RandomVerticalFlip 随机垂直翻转



![images](https://user-images.githubusercontent.com/55572398/82731175-97935a00-9d37-11ea-890a-8f399f9031ee.jpg)


## Pytorch读取数据

<img width="617" alt="截屏2020-05-23 下午9 01 02" src="https://user-images.githubusercontent.com/55572398/82731334-a6c6d780-9d38-11ea-958d-5f681890e4b8.png">

*有了Dataset为什么还要有DataLoder？其实这两个是两个不同的概念，是为了实现不同的功能*。
1.Dataset：对数据集的封装，提供索引方式的对数据样本进行读取
2.DataLoder：对Dataset进行封装，提供批量读取的迭代读取

