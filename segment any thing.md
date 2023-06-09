Motivation

- prompt

- aim to build a foundation model for segmentation and develope a prompt model for segmentation 

Relative Work

# 视觉大模型应该怎么做

## 要做什么任务？

分割任务：

- 与分类一样是视觉的基础任务

- 泛用性高，可以拓展到下游任务

- 可以进行prompt自适应

## 用什么模型

![image-20230515212900543](assets/image-20230515212900543.png)

- image encoder用于获得图片的embedding，是网络的主要开销
- box，point都是稀疏类型，用稀疏向量表示即可，mask是稠密类型需要采用卷积获得编码表示

## 怎么训练

![image-20230515212908309](assets/image-20230515212908309.png)



## 怎么得到数据集



![image-20230515212914571](assets/image-20230515212914571.png)



Methods

- a promptable segmentation task, 

- a segmentation model (SAM) that powers data annotation and enables zero-shot transfer to a range of tasks via prompt engineering, 

- and a data engine for collecting SA-1B, our dataset of over 1 billion masks

![image-20230515212920697](assets/image-20230515212920697.png)



data engine如何构建

如何标注这么大的数据集的？数据集迭代构建的思路：

先用[开源数据集](https://www.zhihu.com/search?q=开源数据集&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A2970661922})训练一个小模型

 标注员用训好的模型辅助标注，优先标好标的。如果图中一个instance开始花费超过30s就可以跳下一张图了

 用新增的label在大模型上重新训练，并重复第2步。随着模型能力的增强，之前难标的会逐渐变成好标的

 第3步迭代6次后，开始攻克剩余所有困难的instance。先用模型把容易的instance都mask掉，剩下的就得拿去标啦。



知乎评价：



![image-20230515212926108](assets/image-20230515212926108.png)

![image-20230515212931279](assets/image-20230515212931279.png)

CV的语义信息属于弱聚合，而NLP的语义是强聚合，这一点来说对cv，多模态是cv大模型的未来：

![image-20230515212939476](assets/image-20230515212939476.png)

[Meta 发布图像分割论文 Segment Anything，将给 CV 研究带来什么影响？ - 知乎 ](https://www.zhihu.com/question/593914819)

