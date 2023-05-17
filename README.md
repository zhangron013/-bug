# -bug&&tips
#### AttributeError: module ‘cv2‘ has no attribute ‘imread‘
大概率是opencv-contrib-python库没装
重装cv2库，注意顺序
先安装 opencv-contrib-python
后安装 opencv-python
~ pip uninstall opencv-contrib-python 

#### yolo多卡训练
单机多卡
python -m torch.distributed.launch --nproc_per_node 2 train.py --batch 64 --data custom.yaml --weights [your pretrained weight] --device 0,1(opts:0-max(gpus))
