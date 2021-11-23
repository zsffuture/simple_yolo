# simple_yolo
- tensorrt实现yolov5的预处理和解码操作，该项目来源Repo：https://github.com/shouxieai/tensorRT_Pro.git
- 在此基础上，本人对其实现进行了全方位的注释和加入了自己的理解，尤其表现在框架架构、预处理和解码方面
- 同时本人会继续完善该注释工作，希望可以帮助大家学习
- 您也可以通过这个repo：https://github.com/Guanbin-Huang/tensorRT_Pro_co-comments.git 拉取，其中simple_yolo保持同步更新

# Simple YoloV5/YoloX
- 更加容易集成的YoloV5/YoloX实现
- 仅依赖官方的tensorRT，无第三方依赖，也没有复杂的封装
- 只有hpp和cu两个文件

# YoloV5
- 请在`export.py`中修改onnx导出时dynamic维度只有batch，去掉images部分的width和height，以及output部分的anchors，只保留batch: -1
- 然后执行跟主项目一样的修改方式
- 再执行导出onnx，并启用--dynamic选项，使得导出的onnx时动态batch。至此导出的onnx即可被这个项目接受
- 如果失败，请对比自动下载的onnx的头部和结尾部分是否一样，保证一样后才能推理正常
- YoloV5的导出命令：
```bash
python export.py --imgsz=640 --weights=yolov5s.pt --include=onnx --dynamic
```

# 关于依赖
# About dependencies
- CUDA10.1
- CUDNN8.2.2.26
- OpenCV3.4.6 or 4.x
  - the above three are modifiable as long as being compatible to TensorRT
- Protobuf3.11.4 (unmodifiable, otherwise problematic)
- tensorrt-8.0.1.6
# For Windows
- Visual Studio 2017 (>=2017)
- [download the lean.rar](http://zifuture.com:1556/fs/sxai/lean.rar).

***

# 关于依赖
- CUDA10.1         （可修改，适配TensorRT即可）
- CUDNN8.2.2.26    （可修改，适配 TensorRT即可）
- OpenCV3.4.6     （可修改）
- Protobuf3.11.4  （不可修改，否则问题多多）
- TensorRT-8.0.1.6

# 对于Windows而言
- Visual Studio 2017  （请大于等于2017）
- [点击下载打包好的lean.rar](http://zifuture.com:1556/fs/sxai/lean.rar)