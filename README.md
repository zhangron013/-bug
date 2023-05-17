# bug&&tips
#### AttributeError: module ‘cv2‘ has no attribute ‘imread‘
大概率是opencv-contrib-python库没装 </br>
重装cv2库，注意顺序
先安装 opencv-contrib-python</br>
后安装 opencv-python</br>
```python
pip uninstall opencv-contrib-python 
pip uninstall opencv-python
pip install opencv-contrib-python 
pip install opencv-python
```

#### yolo多卡训练
单机多卡:</br>
```python
  python -m torch.distributed.launch --nproc_per_node 2 train.py --batch 64 --data custom.yaml --weights [your pretrained weight] --device 0,1(opts:0-max(gpus))
```
参数具体参考train.py里的参数需要，替换即可，主要是 `orch.distributed.launch --nproc_per_node 2` 需要几块卡`nproc_per_node`后面改成几
