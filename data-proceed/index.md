# 数据处理与分析 笔记


## 数据分析理论（业务层）

1. 观测
- 获得数据：测量、爬取、现实场景的抽象与量化。
- 制作报表、图表。
2. 实验
- 提出假设或模型，并验证，解决实际问题。
- 例如A/B测试。
3. 应用
- 创造商业价值。

### 采集

1. 系统日志：埋点获取新数据。
2. 传感器。
3. 主动爬取和检索收集。
4. API获取对象提供的数据。

### 存储

**数据库**种类
- HiveSQL
- MySQL
- SQLserver

### 测量

**场景**
1. 日常维护：发现异常。
2. 研究数据关系。

**流程**
1. 设定标准：判断数据正常与否。
2. 寻找原因。
3. 计算推导相关性。

### 实验

即用数据分析来检验某种假设或求解某个状态或预测指标。

严谨性：重复实验和控制变量。

### 业务应用

1. 明确目标，拆解指标
  法则：MECE（Mutually Exclusive Collectively Exhaustive）即无重复无遗漏
  
  方法：
- 流程拆解：按照时间流程顺序，如用户购买商品的全流程，漏斗分析法。
- 二分拆解：变量属性分两类，如白天/黑夜。
- 象限拆解：横纵坐标二维拆解。
- 杜邦分析：ROE（净资产收益率）=销售净利率*资产周转率*权益乘数。
  
  模型：
- AARRR（Acquisition、Activation、Retention、Revenue、Refer）用户增长（获取、激活、存留、收益、推荐传播）。
- PEST：政治（Politics）、经济（Economic）、社会（Society）、技术（Technology）。
- RFM：根据客户活跃程度和交易金额贡献，进行客户价值细分。（近度-交易间隔，频度-交易次数，额度-金额）。
- SWOT：企业优势（strength）、劣势（weakness）、机会（opportunity）和威胁（threats）。
- 5W1H：Who确定主题，Where进行数据集成，When时间段，What分析方法，Why原因，How (如何呈现结果
2. 准备相关数据：数据库取数，BI搭建看板。
3. 观测：发现问题；实验：验证假设。
4. 制定策略，迭代。

自动化：使用算法针对业务目标自动监测和优化。

## 数据预处理

### 缺失值[^1]

1. 直接删除指标：若缺失太多，直接删除指标，该变量作废；如果本身数据源数量很大，或缺失较少，且剔除缺失指标后，剩余数据的其他变量指标仍然在问题域内有效，也可保留该变量。
2. 替换类似值

- 定量数据，均值
- 定性数据，众数（出现次数最多的值）

3. 插值

- Newton 插值法：但注意存在Runge现象，边缘存在震荡偏差。
- 样条插值：分段光滑曲线逼近，可保持节点光滑，规避突变。

[^1]: 缺失值的处理（数学建模-数据预处理） @数学建模BOOM https://zhuanlan.zhihu.com/p/402497542

## Excel

### 常见问题

1. 单元格右上角红色三角形：链接到注释。
2. 冻结窗格：锁定行列，滚动页面时一直可见。


### 函数[^2]

[^2]: Excel函数公式大全(图文详解) @真假斗士 https://zhuanlan.zhihu.com/p/436372294

#### 计数
- COUNT
- COUNTA（包含逻辑值等）
- COUNTBLANK
- COUNTIF
- COUNTIFS

#### 索引匹配
- LOOKUP
- VLOOKUP

#### 数学和金融函数
- SQRT
- DEGREE
- RAND()
- GCD

#### 逻辑函数
- IF
- AND
- FALSE
- TRUE

#### 日期和时间函数
- NOW()
- DATEVALUE()
- WEEKDAY(NOW())

#### 替换
SUBSTITUTE(text, oldText, newText, [instanceNumber])
REPLACE(oldText, startNumber, NumberCharacters, newText)

### 数据透视表[^3]


[^3]: Excel基础操作 @戴师兄 https://yrzu9y4st8.feishu.cn/mindnotes/bmncnOxqQPowAqr0iPzUZYFTirg

