# 数据库与数据仓库 笔记


<!--more-->

## 数据仓库[^1]

### 模型

1. 星型模型：事实表+维度表
![星型模型](https://pic1.zhimg.com/80/v2-3ab86050013d9381c1555482df933f58_1440w.webp)


### 数据倾斜

大量的数据集中到了一台或者几台机器上计算。

表现
- MapReduce：ruduce阶段卡在99.99%
- Spark：个别task执行极慢

分类
- 频率倾斜：某区域数据量过多
- 大小倾斜：部分记录大小过大


## 实例：尚硅谷-电商数仓[^1]

[^1]: https://www.bilibili.com/video/BV1yY411b72x/?vd_source=e81e93bc6892fd0d7e19b265d26a2b3a


## SQL[^2][^3]

### 常见问题[^4]


[^1]: 尚硅谷物流数仓笔记（数仓基础知识） @橘生淮南 https://zhuanlan.zhihu.com/p/647035072
[^2]: SQL从入门到实战 @戴师兄 https://yrzu9y4st8.feishu.cn/mindnotes/bmncn7s9I4IyCLgrrQCskdP7dRf
[^3]: 数据库（SQL）面试题，基础知识（超全面） @weihubeats https://blog.csdn.net/qq_42651904/article/details/83146345
[^4]: 【SQL】SQL经典50题&答案 @胖熊酱 https://zhuanlan.zhihu.com/p/67645448
