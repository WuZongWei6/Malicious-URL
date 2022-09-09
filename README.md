# 基于CNN的恶意URL识别


## 简介
这是一个基于卷积神经网络（CNN）实现的恶意URL检测/识别算法模型。


## 要求
- paddle
- Python 3
- NVIDIA GPU + CUDA CuDNN

## 数据集
参考[网上的开源数据](https://blog.csdn.net/xyh_qianxiao/article/details/115912690)。

## 算法简介
1. 从CSV文件中读取URL
2. 清洗数据（空数据、url被拆成几行）
3. 数据格式化（去除标点符号、字符小写）
4. 计算url的平均长度m，过长截断，过短补零
5. 使用[Word2Vec](https://en.wikipedia.org/wiki/Word2vec)制作长为128的词向量
6. 用词向量表示截断或补齐后的url ([m, 128]的输入)
7. 使用[VGG](https://arxiv.org/abs/1409.1556)网络，编写成二分类问题


## 结果
<img src=./result.png />


## 使用方法
可在[百度AI Studio](https://aistudio.baidu.com/aistudio/index)上运行或者本地运行

## 其他思路？
LSTM等