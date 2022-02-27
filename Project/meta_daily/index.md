# Penny and penny laid up will be many


### 精选
- [x] [10个开源工业检测数据集汇总](https://mp.weixin.qq.com/s/aV4eZk5hYwrBPsf0y_xS0w)
- [ ] [如何解决工业缺陷检测小样本问题？](https://mp.weixin.qq.com/s/CB-SIFq-5_Q0Lf0o54bgwQ)

- [x] [深度学习框架PyTorch常用代码段](https://mp.weixin.qq.com/s/4breleAhCh6_9tvMK3WDaw)
- [ ] [GitHub 7.5k star量，各种视觉Transformer的PyTorch实现合集整理好了](https://mp.weixin.qq.com/s/aZwmaY8AjdaomETmMfpy2g)
  
---

### 每日学习

### 2022/1/19

- [x] [NAM: Normalization-based Attention Module，一种新的注意力计算方式，无需额外的参数](https://mp.weixin.qq.com/s/MTtTWOIN5G_4ZwMUbSqitg))

### 2022/1/14

- [x] [【他山之石】PyTorch可复现/重复实验的相关设置 ](https://mp.weixin.qq.com/s/xqe-a0-vOVfH-8u_y4CZVA)

### 2022/1/12

- [ ] [一文解决样本不均衡](https://mp.weixin.qq.com/s/ZRpph2VoL6llpkvj6yWewQ)

### 2022/1/11

- [ ] [知识蒸馏综述：代码整理](https://zhuanlan.zhihu.com/p/444664308)

### 2022/1/9

- [x] [PyTorch dataset随机值的完美实践]([PyTorch dataset随机值的完美实践 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/377155682))  

### 2022/1/8

- [ ] [聊聊Pytorch中的dataloader](https://zhuanlan.zhihu.com/p/117270644)

### 2021/12/30
- [ ] [深度学习框架PyTorch常用代码段](https://mp.weixin.qq.com/s/4breleAhCh6_9tvMK3WDaw)

### 2021/12/29
- [x] [pytorch优化器与学习率设置详解](https://mp.weixin.qq.com/s/nz4RdxdG8d8lCJl-hEu6TA)
  ```python
  optimizer = torch.optim.SGD(model.parameters(), lr=0.1, momentum=0.9)
  scheduler = ReduceLROnPlateau(optimizer, 'min')
  for epoch in range(10):
      train(...)
      val_loss = validate(...)
      # Note that step should be called after validate()
      scheduler.step(val_loss)
  ```

### 2021/12/23
- [x] [Pytorch 数据流中常见Trick总结](https://zhuanlan.zhihu.com/p/441317369)
  ```
  解决如果__getitem不是对其的tensor怎么办？
  DataLoader会自动合并__getitem__ 方法返回的字典内每个key内每个tensor，在tensor的第0维度新增一个batch大小的维度。如果该方法返回的每条样本长度不同无法拼接，batchsize>1就会报错。但是又一些任务在还没有确定后续的批样本对应的任务时，Dataset可能返回的字典里每个key可能就是长度不同的tensor，甚至是list，这时候需要使用collate_fn参数告诉DataLoader如何取样。我们可以定义自己的函数来准确地实现想要的功能。
  
  如果__getitem__方法返回的是tuple((list, list)) 可以使用
  ```
### 2021/12/22
- [ ] [推荐!!CNN结构设计技巧-兼顾速度精度与工程实现](https://mp.weixin.qq.com/s/a3dwhUbNaRDhidDBZvdLMw)
- [x] [PyTorch可复现/重复实验的相关设置](https://zhuanlan.zhihu.com/p/448284000)

    ```python
    # PyTorch
    import torch
    torch.manual_seed(0)
    
    # python
    import random
    random.seed(0)
    
    # Third part libraries
    import numpy as np
    np.random.seed(0)
    
    #GPU
    # 不需要benchmarking
    torch.backends.cudnn.benchmark=False
    
    # 选择确定性算法
    torch.use_deterministic_algorithms() 
    
    # 样本读取随机
    # 多线程情况下，设置每个线程读取的随机种子
    # 设置样本generator
    # 设置每个读取线程的随机种子
    def seed_worker(worker_id):
        worker_seed = torch.initial_seed() % 2**32
        numpy.random.seed(worker_seed)
        random.seed(worker_seed)
    
    g = torch.Generator()
    # 设置样本shuffle随机种子，作为DataLoader的参数
    g.manual_seed(0)
    
    DataLoader(
        train_dataset,
        batch_size=batch_size,
        num_workers=num_workers,
        worker_init_fn=seed_worker,
        generator=g,
    )
    
    ```

### 2021/12/17
- [ ] [Self-Attention和CNN的优雅集成！清华大学等提出ACmix，性能速度全面提升！](https://zhuanlan.zhihu.com/p/440510903?utm_source=wechat_session&utm_medium=social&utm_oi=672184783560380416)

### 2021/12/16
- [ ] [用torchvision训练一个SOTA的ResNet](https://zhuanlan.zhihu.com/p/436518994?utm_source=wechat_session&utm_medium=social&utm_oi=824054350027554816&utm_campaign=shareopn)

- [ ] [学生网络用知识蒸馏损失去逼近教师网络，如何提高学生网络的准确率？](https://www.zhihu.com/question/386173051/answer/2268710658?utm_source=wechat_session&utm_medium=social&utm_oi=824054350027554816&utm_content=group3_Answer&utm_campaign=shareopn)

- [ ] [通道注意力超强改进，轻量模块ECANet来了！即插即用，显著提高CNN性能｜已开源](https://zhuanlan.zhihu.com/p/153112149?utm_source=wechat_session&utm_medium=social&utm_oi=824054350027554816&utm_campaign=shareopn)

- [ ] [再谈softmax和对比学习](https://zhuanlan.zhihu.com/p/441985870?utm_source=wechat_session&utm_medium=social&utm_oi=824054350027554816&utm_campaign=shareopn)

- [ ] [仅需12层网络，ParNet在ImageNet上准确率达到80.7%！（附完整代码实现）](https://zhuanlan.zhihu.com/p/445683480?utm_source=wechat_session&utm_medium=social&utm_oi=824054350027554816&utm_campaign=shareopn)

- [ ] [老文重发：我的PhD总结暨关于PhD的十个问题](https://zhuanlan.zhihu.com/p/438640120?utm_source=wechat_session&utm_medium=social&utm_oi=824054350027554816&utm_campaign=shareopn)

- [ ] [ICCV2021】CrossViT: Cross-Attention Multi-Scale Vision Transformer for Image Classification
高峰OUC](https://zhuanlan.zhihu.com/p/444799438?utm_source=wechat_session&utm_medium=social&utm_oi=824054350027554816&utm_campaign=shareopn)

- [ ] [做科研到底应不应该灌水？](https://www.zhihu.com/question/273953521/answer/2246266820?utm_source=wechat_session&utm_medium=social&utm_oi=824054350027554816&utm_content=group3_Answer&utm_campaign=shareopn)

- [ ] [两个小模型就能吊打大模型！北大校友、谷歌华人一作「模型集合」，CNN、Transformer都适用！](https://zhuanlan.zhihu.com/p/434798566?utm_source=wechat_session&utm_medium=social&utm_oi=824054350027554816&utm_campaign=shareopn)

### 2021/12/15
- [x] [实践教程 | 浅谈 PyTorch 中的 tensor 及使用](https://mp.weixin.qq.com/s/6Q6LrRwGmGZ7Qs72hVNE7A)
```python
tensor.to(device)
tensor.detach()
tensor.require_grad
tensor.item()
tensor.tolist()
with torch.no_grad():
```


### 2021/12/13

- [ ] [Transformer代码+面试细节](https://mp.weixin.qq.com/s/x73m8caXjj-iqC9XsvHa0g)

- [ ] [史上最细节的自然语言处理NLP/Transformer/BERT/Attention面试问题与答案](https://zhuanlan.zhihu.com/p/348373259)
