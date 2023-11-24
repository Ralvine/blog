# 🏫


<div class="nav-tab">
  <a href="../../../cages"><p class="not">拾迹</p></a><p class="not">/</p>
  <a href="../"><p class="not">课程</p></a>
  <p class="now">/</p><p class="now">微分方程数值解</p>
</div>

---

{{< admonition question "课程信息" true false >}}
🎓 数学科学学院<br>
🕙 2022-2023 春夏<br>
🧑‍🏫 张庆海<br>
📝 40%平时，60%期末
{{< /admonition >}}

{{< admonition tip "参考资料" true false >}}
📑 教材讲义<br>
💻 [智云课堂](https://classroom.zju.edu.cn/coursedetail?course_id=51564&tenant_code=112)
{{< /admonition >}}

{{< admonition success "教学大纲" true false >}}
- **Ch7** BVP-FD
    - 有限差分离散化
    - 误差和一致性
    - 稳定性、收敛性
        - 范数收敛
        - Green函数
            - 解决方案
    - 其他边值条件
    - 二维
        - Kronecker乘积
        - 范数收敛性
    - 不规则边界、收敛性
- **Ch9** Multigrid
    - 残差方程
    - 模型问题
    - 算法组成
        - 傅立叶模式
        - 松弛
        - 限制、延拓
        - 双网格矫正
        - 多重网格cycles
    - 收敛性分析
        - 代数图
        - FMG最优复杂度
- **Ch11** IVP
    - 数学基础
        - ODE
        - 算子范数
        - 矩阵指数
        - Lipschitz连续条件
        - 解的唯一存在性
        - well-posed 适定性
        - 常系数线性IVPs
    - 数值方法
        - 欧拉法
        - 前欧拉
        - 后欧拉
        - 梯形法
        - leapfrog 中点法
        - 截断误差
        - 欧拉法的收敛性
        - 零/绝对稳定性
    - 线性多步法
        - 一致性、稳定性
        - 零稳定性
        - 线性差分方程
        - 收敛性
        - 绝对稳定性
    - 刚性IVPs
        - 刚度 stiffness
        - A-稳定性
    - 单步法
        - 一致性、收敛性
        - 绝对稳定性
        - A-稳定性、L-稳定性
    - 龙格库塔法
        - 显式法
        - 必要阶数条件
        - 隐式法
        - Collocation 配点法
        - 实用误差估计、步长控制
        - 一致性、收敛性
        - 绝对稳定性
        - I-稳定性、L-稳定性
        - 收缩性、B-稳定性
        - 代数稳定性
- **Ch12** MOL
    - 热方程
        - 抛物、导出
        - 边值条件、精确解
        - FTCS
        - Crank-Nicolson
        - 精度、一致性
        - 绝对稳定性、Lax-Richtmyer稳定性
        - 收敛性
        - 离散最大值原理
        - 冯诺依曼稳定性
    - 平流方程
        - 经典MOL法
            - FTCS
            - leapfrog
            - Lax-Friedrichs
            - Lax-Wendroff
            - upwind
            - Beam-Warming
        - CFL条件
        - 修正方程
        - 冯诺依曼分析
{{< /admonition >}}

{{< admonition info "作业" true false >}}
🗞️ 讲义章节习题<br>
🗞️ 章节编程项目
{{< /admonition >}}

<!--
{{< admonition failure "笔记" true false >}}
{{< /admonition >}}

{{< admonition note "经验" true false >}}
{{< /admonition >}}
-->


