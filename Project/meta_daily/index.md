# This is index test Pages

电脑的双内存一定要安装在双通路上，不临近


### 2021/12/23
- [x] [Pytorch 数据流中常见Trick总结](https://zhuanlan.zhihu.com/p/441317369)

解决如果__getitem不是对其的tensor怎么办？
DataLoader会自动合并__getitem__ 方法返回的字典内每个key内每个tensor，在tensor的第0维度新增一个batch大小的维度。如果该方法返回的每条样本长度不同无法拼接，batchsize>1就会报错。但是又一些任务在还没有确定后续的批样本对应的任务时，Dataset可能返回的字典里每个key可能就是长度不同的tensor，甚至是list，这时候需要使用collate_fn参数告诉DataLoader如何取样。我们可以定义自己的函数来准确地实现想要的功能。

如果__getitem__方法返回的是tuple((list, list)) 可以使用

### 2021/12/22
- [ ] [推荐!!CNN结构设计技巧-兼顾速度精度与工程实现](https://mp.weixin.qq.com/s/a3dwhUbNaRDhidDBZvdLMw)
- [x] [PyTorch可复现/重复实验的相关设置](https://zhuanlan.zhihu.com/p/448284000)


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
