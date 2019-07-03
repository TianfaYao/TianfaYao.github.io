# TianfaYao


## Stereo Visual Simultaneous Localization and Mapping 
  - 采用[Euroc](https://projects.asl.ethz.ch/datasets/doku.php?id=kmavvisualinertialdatasets)数据集作为算法验证
  - 前端设计采用光流跟踪
  - 后端采用Sliding window,优化器采用g2o

![image](image/without_loop_close.gif)

### 在数据集上更多测试视频
[video1](https://www.bilibili.com/video/av57411730) 
[video2](https://www.bilibili.com/video/av57410811)

## stereo vins on wheel 
- 在上述算法验证完成的基础上采用[小觅](http://www.myntai.com/product/customize)双目相机作为基础硬件，搭载在AGV小车上;
- 为了得到更好的精度和鲁棒的面对室内环境采用紧耦合的方式融合了轮速计和imu(z)，完成传感器内外参标定，融合因子图建立，以及数学模型推导验证。
- 在后端加入DBow进行回环检测,如果检测到回环进行pose-graph优化，加入DBow检测后也完成了重定位，以及地图保存后加载进行纯定位模式。

![image](image/stereo_odom_add_plant_small_dataset.gif)


