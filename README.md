# AutoStitcher
This repository is our C++ implementation of the *IJCV 2007* paper [Automatic Panoramic Image Stitching using Invariant Features](http://matthewalunbrown.com/papers/ijcv2007.pdf).

这是我们项目代码仓库，主要基于Brown在IJCV2007的论文[Automatic Panoramic Image Stitching using Invariant Features](http://matthewalunbrown.com/papers/ijcv2007.pdf)实现。

## 算法模块

![algorithm flow](https://github-1252003451.cos.ap-shanghai.myqcloud.com/github/AutoStitch.png)

## 算法流程

输入：n（2或3）张有序图片
- 从n张图片中提取SIFT特征点
- 使用k-d数算法为每个特征点找到k近邻相似点
- 针对所有图片
  - 使用RANSAC算法计算特征点匹配对之间的2D映射关系H（单应矩阵）
  - 使用概率模型验证图片匹配对
- 针对所有图片进行捆绑调整，计算得到相机的三维旋转矩阵角度theta1，theta2，theta3和所有相机的角度f
- 多通带融合全景图

输出：全景图