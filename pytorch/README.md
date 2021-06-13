# 2021中国高校计算机大赛-微信大数据挑战赛Baseline（Pytorch版）

代码实现基于[DeepCTR](https://github.com/shenweichen/DeepCTR-Torch)，只做了简单数据预处理，采用的是基本特征（离散特征：{'userid', 'feedid', 'authorid', 'bgm_song_id', 'bgm_singer_id'}，连续特征：{'videoplayseconds'}），单个任务逐个预测，大家可以尝试改进原有的模块，并尝试新的模型和新的建模方法。
baseline纯为学习和参考，有什么做的不对的地方，还请大佬们批评和指正😄

## 1.环境配置
- python3
- torch 1.6
- deepctr-torch 0.2.6
- pandas 1.0.1
- scikit-learn 0.22.1

## 2.运行配置
- CPU/GPU均可
- 最小内存要求
  - 特征/样本生成：6G
  - 模型训练及评估：4G

## 3.目录结构
- prepare_data.py 数据集生成
- baseline.py: 模型训练，评估，提交

## 4.运行流程
- 新建data目录，下载比赛数据集，放在data目录下并解压，得到wechat_algo_data1目录
- 数据集生成：运行prepare_data.py
- 模型训练，评估，提交：运行baseline.py

## 5.模型及参数
模型：DeepFM

参数：
batch_size: 512

optim: Adagrad

num_epochs: 5

learning_rate: 0.1


## 6.模型结果
我的线下验证集评价指标还没有改成和官网一致的方法，所以参考意义不大，需要大家重写评估方法

线上：
| weight_uauc | read_comment | like    | click_avatar | forward  |
| ----------- | ------------ | ------- | ------------ | -------- |
| 0.640712    | 0.624132     | 0.61151 | 0.705983     | 0.664097 |

## 7.相关文献
Guo H, Tang R, Ye Y, et al. Deepfm: a factorization-machine based neural network for ctr prediction[J]. arXiv preprint arXiv:1703.04247, 2017.
