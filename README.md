# 第6次课 RFID系统测量模型
## RFID的测量特性

![RFID测量模型](https://github.com/Xue-boJin/data-fusion-for-indoor-tracking-by-RFID/blob/resource/RFIDmodel.png)
我们先来看右边第1个公式，这里描述的是携带标签的目标到阅读器的距离。但是由于传感器的测量噪声，使得阅读器获得的距离不是这个真实距离，而是加上一个测量噪声，也就是，公式2表示的。这个测量噪声的方差和距离有关，也就是说距离越长，所引入的测量噪声方差就会越大，越不准确，它的描述方法见公式3。
## RFID跟踪系统的机动目标轨迹模拟
RFID跟踪系统仿真平台见Matlab程序![RFID_creater_GUI_final.m](https://github.com/Xue-boJin/data-fusion-for-indoor-tracking-by-RFID/blob/Lesson2/RFID_creater_GUI_final.m)。

# 第6次课 非线性估计

## EKF

EKF使用泰勒级数展开的方法，将非线性关系变成了线性关系。当然啦，只取了1阶变换，因此，可以知道，如果非线性特别严重的话，1阶近似就不太好啦！！

![EKF算法](https://github.com/Xue-boJin/data-fusion-for-indoor-tracking-by-RFID/blob/Lesson3/EKFpng.png)

##UKF
UKF使用一种叫“不敏变换”（Sigma Transform）将非线性的点“爆炸”成若干个点，就是这样的：![不敏变换](https://github.com/Xue-boJin/data-fusion-for-indoor-tracking-by-RFID/blob/Lesson3/UKF0.png)。![不敏变换的示意图](https://github.com/Xue-boJin/data-fusion-for-indoor-tracking-by-RFID/blob/Lesson3/UKFFigure.png)
然后每一步都是这多个点进行估计，再计算方差，这可是复杂多了！！
![UKF](https://github.com/Xue-boJin/data-fusion-for-indoor-tracking-by-RFID/blob/Lesson3/UKF1.png)
![UKF](https://github.com/Xue-boJin/data-fusion-for-indoor-tracking-by-RFID/blob/Lesson3/UKF2.png)

参考文献

[1] 金学波，![Kalman滤波器理论与应用——基于MATLAB实现](http://www.ecsponline.com/goods.php?id=177510)，科学出版社，2016，第5章、第8章
