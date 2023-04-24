# Revisiting Weak-to-Strong Consistency in Semi-Supervised Semantic Segmentation

> 改进半监督学习中的FixMatch,可以作为baseline的一个有趣的A+B工作

<img src="C:\Users\wrq\Desktop\坚果云同步\我的坚果云\Rainbell English1\Rainbell English\paper\paper_notes\image\image-20230423172512037.png" alt="image-20230423172512037" style="zoom:50%;" />

解决的问题：半监督语义分割

insight：半监督语义分割的经典方法FixMatch本身就具有相当好的结果

对其消融发现，强扰动尤为重要

过去的方法：仅仅在输入强扰动

我们的做法：FixMatch只在**输入空间（图像）\**上进行了强扰动，因此我们提出进一步去扩展FixMatch的扰动空间，增加了一个训练分支来进行\**特征空间**上的强扰动

<img src="C:\Users\wrq\Desktop\坚果云同步\我的坚果云\Rainbell English1\Rainbell English\paper\paper_notes\image\image-20230424111006116.png" alt="image-20230424111006116" style="zoom:50%;" />

和过去方法的独特之处：

- “也有一些工作如PS-MT同时进行了图像和特征上的强扰动，然而他们将这些强扰动施加在了同一个分支中，导致学习的难度过大；而我们将不同性质的强扰动分离到不同的分支分别进行学习“     

- 相比于一些特征扰动的工作如VAT，我们的特征Dropout策略更简单有效。

![image-20230424111558284](C:\Users\wrq\Desktop\坚果云同步\我的坚果云\Rainbell English1\Rainbell English\paper\paper_notes\image\image-20230424111558284.png)

具体做法：针对无标签图像，UniMatch一共包括四个前向传播分支，其中有一个“干净”的分支来产生伪标签、一个特征层面的强扰动分支（作用于 *x**w* 的特征上），以及两个图像层面的强扰动分支（无特征扰动）。其中后三个分支用于网络的训练（此图中我们省略了有标签图像的训练分支）。



Overall：多分支扰动[SWAV ReMixMatch]和特征空间扰动[PS-MAT]



