# 简易神经网络实现MNIST手写数字识别

## 1. 介绍

本文档描述了一个用C语言实现的简单神经网络，主要用于手写数字识别。该网络包含一个输入层、一个隐藏层和一个输出层。我们使用MNIST数据集进行训练和测试。

## 2. 环境要求

- C编译器
- MNIST数据集

## 3. 文件结构

- `nn.c`: 包含神经网络的主要实现代码。

## 4. 代码实现

### 4.1 宏定义和结构体声明

我们定义了一些常量，如输入层大小、隐藏层大小、输出层大小、学习率等。还声明了两个结构体 `Layer` 和 `Network`，分别用于表示神经网络的一层和整个网络。此外，还声明了 `InputData` 结构体，用于存储MNIST数据集的图像和标签。

### 4.2 辅助函数

- `softmax`: 对输入数据进行softmax归一化。
- `init_layer`: 初始化一层网络，包括权重和偏置。
- `forward`: 前向传播，计算一层网络的输出。
- `backward`: 反向传播，计算梯度并更新权重和偏置。
- `train`: 训练网络，进行一次前向和反向传播，并更新权重。
- `predict`: 使用训练好的网络进行预测。
- `read_mnist_images` 和 `read_mnist_labels`: 读取MNIST数据集的图像和标签。
- `shuffle_data`: 打乱数据集。

### 4.3 主函数

主函数的主要流程如下：

1. 初始化网络和随机数种子。
2. 读取MNIST数据集并打乱。
3. 划分训练集和测试集。
4. 进行多次迭代的训练，每次迭代中计算损失和准确率，并打印结果。
5. 释放分配的内存。

## 5. 使用方法

1. 将MNIST数据集放在 `data` 文件夹下。
2. 编译并运行 `nn.c`。

## 6. 训练结果

训练过程中，我们将打印每个epoch的准确率和平均损失。

## 7. 清理

训练完成后，程序将释放所有分配的内存。

## 8. 注意事项

- 请确保MNIST数据集的路径正确。
- 本程序不包含任何错误处理机制，因此在读取文件或内存分配失败时，程序将直接退出。

## 9. 参考资料

- MNIST数据集: http://yann.lecun.com/exdb/mnist/

## 10. 许可

本项目遵循MIT许可协议。

代码位置：[nn.c](nn.c)