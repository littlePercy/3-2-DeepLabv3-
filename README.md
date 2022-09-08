![deeplabv3+](https://user-images.githubusercontent.com/52816016/189051711-6f1e8479-48b0-4865-bdf8-b55d7a23f0c9.png)
# DeepLabv3-
基于pytorch的DeepLabv3+语义分割实现
DeepLab系列从v1-v3+作为语义分割邻域中经典的网络模型，而V3+作为Deeplab所有思想的一个集合，实现Deeplabv3+也是入门语义分割邻域一个重要的知识点。

回顾DeepLabv1-v3
deepLabv1
DeepLabv1提出了深度卷积神经网络（DCNNs）与CRF相结合用于语义分割。DCNNs对目标做粗略分割，CRF做精细分割。由于本文主要针对深度卷积神经网络，因此只对深度卷积神经网络进行介绍。CRF作为DCNNs的后处理，在v3版本后的Deeplab系列也取消了CRF后处理机制。
DeepLabv1针对下采样会使得特征图尺寸减少，特征图尺寸减少对于语义分割效果有很大的影响。Deeplabv1通过修改最后几层的池化操作，在不改变特征图尺寸的前提下，提出空洞卷积，在不增加参数量的同时，获得更大的感受野，从而得到更加丰富的多尺度信息。

deepLabv2
DeepLabv2在v1的基础上针对分割目标具有多尺度大小的特征，使用不同空洞率的空洞卷积，并且借鉴SPP模型结构，提出空洞金字塔池化结构（ASPP)，解决对于多尺度目标分割的问题。
在DCNNs还是加入了CRF用于提高目标边界细节的分割。

deepLabv3
DeepLabv3的主要工作是改进了ASPP模块，提出串联或者并联ASPP模块中不同采样率的空洞卷积，并且在空洞卷积后加入BatchNormalize。并且文章中发现过大的采样率会使用33的空洞卷积退化为11卷积，因此将特征融合加入到ASPP模块中。

deepLabv3+
DeepLabv3+结合之前DeepLab系列的思想，提出编码-解码结构用于语义分割。在编码器阶段使用Xception结构以及ASPP结合作为图像的特征提取，在Xception模型中采用深度可分离卷积降低参数量。

————————————————
版权声明：本文为CSDN博主「卡子爹」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/weixin_44422920/article/details/120709729
