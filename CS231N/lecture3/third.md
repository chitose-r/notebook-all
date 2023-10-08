1. 今天主要讲如何定量构造损失函数/优化策略，进而求出每个权重的调节方向，为卷积神经网络奠定基础
2. 学习playground-tensorflow的网站
3. 数据分布有同心圆、异或、线性类
4. 线性分类器可以对线性类得到很好的分类，但是对异或、同心圆也无法分类
5. 铰链损失函数hinge loss:
   - ![铰链损失函数](image.png)
   - 错误-正确+1与0取最大作为损失值
   - 惩罚跟正确值差1以上的分数类别，惩罚差值小于0的
   - 最后算平均值就是数据集的损失函数
   - 1是有讲究的，可以看官网笔记
   - Python的代码如下：
   - ![铰链损失函数代码](image-1.png)
6. 当L=0时，W可以为很多套权重
   - 越简单越好，选数小的
   - 引入正则化
7. 强度用λ控制，让参数更加简单不要那么大
   - L2正则化：每个权重平方求和
   - L1正则化：每个权重绝对值求和
   - 弹性网络；β来进行L1、L2的权重
8. 正则化的原因：
   - 防止过拟合，防止在训练集做的太好了！
   - 让其在测试集做的更好
   - 我们需要一个大而化之的泛化，不想要做的太好
9.  防止过拟合的其他方法：
   - DropOut(掐死其他神经元)
   - Batch normalization
   - Stochastic depth, fractional pooling, etc
10. Softmax Classifier(多分类的逻辑sigmod回归)
    - 想要将分数值变为概率
    - 