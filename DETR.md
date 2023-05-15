# DETR

view object detection as a set prediction

anchor×   NMS×

- 新的目标函数
- encoder-decoder的transformer架构

过去的方法：作者认为od就是一个集合预测的问题{类别，坐标1，坐标2，坐标3，坐标4}

- 过去的od方法都是间接的处理这个集合预测的问题,根据一些已有的初始的猜测比如    proposal：（two stage） fastRCNN/anchor（one stage）：YOLO/windown centers：centor 这些要么是回归要么是分类而且非常依赖最初的猜测以及post-processing，使得检测的流程非常复杂

- 过去集合预测做od的，性能低，为了提高性能，需要人工加很多先验，DETR的目标是使得od的流程变得简单

- 过去也有用encoder+decoder做od的，用RNN实现这种自回归模型，时效性差，并且没有全局信息。



![image-20230424190041740](C:\Users\wrq\Desktop\坚果云同步\我的坚果云\Rainbell English1\Rainbell English\paper\paper_notes\image\image-20230424190041740.png)

DETR怎么做的：

- CNN：抽特征

- encoder:全局建模

- decoder：通过object query限定产生多少的框

- loss：先进行二分图匹配，再计算分类loss+bbox loss

![image-20230424190443655](C:\Users\wrq\Desktop\坚果云同步\我的坚果云\Rainbell English1\Rainbell English\paper\paper_notes\image\image-20230424190443655.png)

![image-20230424190437128](C:\Users\wrq\Desktop\坚果云同步\我的坚果云\Rainbell English1\Rainbell English\paper\paper_notes\image\image-20230424190437128.png)

实验：



由于全局建模，大物体mAP效果，但是小物体的mAP不好

参考·之前FPN的做法：多尺度特征解决小物体识别难的问题

训练太慢









贡献：

- 新的解决问题的角度 --> set prediction

- encoder-decoder架构

- 匹配+loss函数
