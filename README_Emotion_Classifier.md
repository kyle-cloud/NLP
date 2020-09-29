- [第一部分：任务概述](#第一部分任务概述)
- [第二部分：数据集说明](#第二部分数据集说明)
- [第三部分：相关工具学习](#第三部分相关工具学习)
  - [1 torchtext](#1-torchtext)
    - [1.1 torchtext](#11-torchtext)
    - [1.2 torchtext.data](#12-torchtextdata)
    - [1.3 torchtext.datasets](#13-torchtextdatasets)
    - [1.4 torchtext.vocab](#14-torchtextvocab)
    - [1.5 torchtext.utils](#15-torchtextutils)
    - [1.6 Example](#16-example)
    - [1.7 本项目使用](#17-本项目使用)

## 第一部分：任务概述
    识别微博文本中蕴含的情绪，并分类到一下六种之一：积极、愤怒、悲伤、恐惧、惊奇和无情绪

情绪|样例文本
:-|:-
积极(happy)|愿大家都健康平安
愤怒(angry)|太让人气愤了
悲伤(sad)|受不了泪奔了，太辛苦了
恐惧(fear)|这传播速度太恐怖
惊奇(surprise)|太令人震惊了，竟然还有人不当回事？
无情绪(neural)|不信谣，不传谣

## 第二部分：数据集说明
    1. 来源：疫情期间使用想逛关键字筛选获得的疫情微博，内容与新冠疫情相关
    2. 标签：每条微博为以下六个标签之一：积极happy(积极)、angry(愤怒)、sad(悲伤)、fear(恐惧)、surprise(惊奇)、neural(无情绪)
    3. 规模：训练集6,606条微博，测试集5,000条微博
    4. 形式：json格式，包含三个字段：id(数据编号)，content(文本)和label(情绪标签)
    例：{"id": 1, "content": "天使", "label": "happy"}

## 第三部分：相关工具学习
    在这里记录一下根据官方文档学习相关工具的过程

### 1 torchtext
    官方文档：https://torchtext.readthedocs.io/en/latest/index.html

#### 1.1 torchtext
    包括数据处理工具和流行的数据集

#### 1.2 torchtext.data
    数据预处理、构建词汇表、划分数据集、加载数据集

    Dataset, Batch, and Example
    1. Example:一个简单的训练样例或测试样
    2. Batch:一批样例
    3. Dataset:定义的包含全部样例的数据集
    4. TabularDataset:表格化的数据集，有CSV、TSV和JSON格式

    Fields
    1. RawField:定义一个通用数据类型
    2. Field:定义一个可以转化到Tensor的数据类型
    3. NestedField:嵌套形式

    Iterators
    1. Iterator:定义了一个迭代器从一个Dataset加载batches of data
    2. BucketIterator:加载相似长度的examples
    3. BPTTIterator:为使用BPTT(back-propagation through time)的语言模型任务定义的一个迭代器

    Pipeline:定义了传送序列数据的管道

    Functions
    1. batch:不断地yield一个batch_size大小的数据块
    2. pool:每100*batch_size为一组并组内排序，然后再batch和shuffle

#### 1.3 torchtext.datasets

    数据集就不在这里详细介绍了

#### 1.4 torchtext.vocab
    1. Vocab:定义一个词汇表对象
    2. SubwordVocab:对Subword(基本单元介于字符和单元之间的模型，可以更好地处理未知和罕见的词汇)，创建的词汇表
    3. Vectors:词向量
    4. GloVe:Global Vectors, 向量化表示的模型
    5. FastText:一种快速文本分类算法
    6. CharNGram:统计不同字符出现次数的计数矩阵
    7. pretrained_aliases:预训练化名，使用dict预定义

#### 1.5 torchtext.utils
    1. reporthoot:进度条显示
    2. download_from_url:下载文件

#### 1.6 Example
    一些常见的实际操作

#### 1.7 本项目使用
    `print("?")`


















