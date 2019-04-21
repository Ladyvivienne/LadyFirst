# Git
    git是分布式版本控制系统。 什么是分布式？
##### 定义：
* 分布式系统是若干独立计算机的集合。
* 通过网络进行信息交换的系统。（■种子库？）
* 一个大系统，拆分成多个子系统（process），分布到不同设备通信。（■网络替代本地实现共享？）
##### 特性：
* 分布式系统，通过多台机器<u>提高系统的负载能力</u>。
* 因为有了分布，一个子系统坏了不会影响其他系统。每一次的提取操作，实际上都是一次对代码仓库的完整备份。所以<u>运维可靠</u>。
* 分布式系统的四大要素：<u>Process进程</u>、<u>通信协议</u>、<u>命名法</u>、<u>协作</u>。
##### 难点
* 分布式系统 vs 集中式系统，集中式系统没有分布式的特性。
* 分布式不等于并行计算。
  
```
了解git的基本原理。
```

##### Git的由来

* Github是一个开放源码的分布式控制系统，当初被开发，是为了替代Bitkeeper（遍布全球的Linux开发成员，用此作为源代码工具）。
* Git的两个主要功能：
  1. 版本管理
  版本控制是一种记录若干文件内容变化，以便将来查阅特定版本修订情况的系统。即修改/删除代码后的新项目，上传到github托管，能追踪历史和还原，实现方式为Repositionery里的file。
  2. 协作开发
  同步大家更新的版本，一直存储最新的代码库，所以有了fork功能。
  
##### Git的特性
  
* Git只关心文件数据的<u>整体是否发生变化</u>
  大多数其他系统则只关心文件内容的具体差异，而Git 更像是把变化的文件作快照后，记录在一个微型的文件系统中。每次提交更新时，它会纵览一遍所有文件的指纹信息并对文件作一快照，然后保存一个<u>指向这次快照的索引</u>。
* Git支持离线工作
  本地操作→本地提交→再上传到服务器上。
  Git对修改文件进行快照→保存到暂存区域→提交更新，快照永久转储到 Git 目录。（■快照是哪个？）
* Git的三种文件形态
  已提交（Committed）、已修改（modified）、已暂存（staged）。

##### Git的使用流程

* Fork一个自己喜欢的项目。
* 建立本地的资源池（Local Repo），将项目clone到本地（SSH/HTTP形式）。
* Clone完成后，一个名为“origin”的远端生成指向我在github的版本，此时需要另一个远端“upstream”来获取原始项目的更新。
* 推送提交Push Commits。
  
  
  
```
学会用GUI界面操作，add、commit、push、brach、stash的用法。
```

本来设了一个trial文件，想clone到本地push commit。

结果，把trial文件在github上也搞没了。

我不明白，自己做了什么骚操作。