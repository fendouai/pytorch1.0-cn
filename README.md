# pytorch1.0-cn
pytorch1.0官方文档 中文版

## 概述

PyText 是一个基于 PyTorch 实现的 NLP 框架。PyText 解决了实现快速实验和在规模部署服务模型的冲突。它通过为模型组件提供简单和可扩展的接口和抽象，以及使用通过 PyTorch 优化的 Caffe2 执行引擎可以导出用于推断的模型的能力，来实现这一点。我们使用 Facebook 中的 PyText 来快速迭代新的建模思想，然后无缝地将它们弹性发布。

## PyText 核心特性：

针对NLP/NLU 任务的各种生产就绪的模型：

文本分类器

Yoon Kim (2014): Convolutional Neural Networks for Sentence Classification
Lin et al. (2017): A Structured Self-attentive Sentence Embedding

序列标记

Lample et al. (2016): Neural Architectures for Named Entity Recognition

联合意图槽模型

Zhang et al. (2016): A Joint Model of Intent Determination and Slot Filling for Spoken Language Understanding

上下文意图槽模型

支持建立在 PyTorch 1.0 上新的 C10d 后端分布式训练

可扩展组件，允许轻松创建新模型和任务

参考实现和论文的预训练模型：Gupta et al. (2018): Semantic Parsing for Task Oriented Dialog using Hierarchical Representations

增强训练支持


## 安装 PyText

要开始使用云虚拟机，请查看我们的指南：https://pytext-pytext.readthedocs-hosted.com/en/latest/installation.html#cloud-vm-setup

我们建议使用 virtualenv：
```
  $ python3 -m venv pytext_venv
  $ source pytext_venv/bin/activate
  (pytext_venv) $ pip install pytext-nlp
```
详细说明和更多的安装选项可以在我们的文档（https://pytext-pytext.readthedocs-hosted.com/en/latest/installation.html）中找到。如果在安装过程中遇到缺少依赖项的问题，请参考OS（https://pytext-pytext.readthedocs-hosted.com/en/latest/installation.html#os-dependencies）依赖项。



## 训练第一个文本分类器

对于第一个例子，我们将使用基于 CNN 的文本分类器，我们将使用 tests/data/train_data_tiny.tsv。可以通过克隆存储库或通过从GitHub手动下载文件来获得数据和配置文件。
```
（venv）$pytext.<demo/configs/docnn.json
```
默认情况下，在 /tmp/model.pt 中创建模型。

现在，您可以将模型导出为 caffe2 net：
```
  (venv) $ pytext export < config.json
```
您可以使用导出的 caffe2 模型来预测如下文本的类别：
```
  (venv) $ pytext --config-file config.json predict <<< '{"raw_text": "create an alarm for 1:30 pm"}'
```
更多示例和教程可以在完整文档（https://pytext-pytext.readthedocs-hosted.com/en/latest/）中找到。



## 加入社区

•Facebook group:https://www.facebook.com/./pytext/

## 项目地址：
https://github.com/facebookresearch/pytext


