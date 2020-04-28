### 开发环境

- Python 3.6

- PyTorch v0.4.1.  

  

0. 创建一个虚拟环境并激活

```bash
# 创建一个虚拟环境
conda create --name CenterNet python=3.6
# 激活环境
conda activate CenterNet
```



1. 安装 PyTorch

```bash
# 安装 pytorch0.4.1
conda install pytorch=0.4.1 torchvision -c pytorch
```

2. 安装 COCOAPI

```bash
git clone https://github.com/cocodataset/cocoapi.git 
cd cocoapi/PythonAPI
make
python setup.py install --user
```



3. git 项目

```bash
git clone https://github.com/FLyingLSJ/CenterNet.git
cd CenterNet

```

4. 安装必要包

```bash
pip install -r requirements.txt
```

5. 编译可形变卷积 (from [DCNv2](https://github.com/CharlesShang/DCNv2/tree/pytorch_0.4)). 

```bash
cd CenterNet/src/lib/models/networks/DCNv2
./make.sh
```

6. [可选：如果想使用多尺度进行训练或者测试的话] 编译 NMS

```bash
cd CenterNet/src/lib/external
make
```

7. 下载预训练模型（只针对目标检测）

```bash
cd CenterNet/models
sh download_model.sh
```

8. 测试

```bash
python demo.py ctdet --demo ../images --load_model ../models/ctdet_coco_dla_2x.pth --debug -1
```







