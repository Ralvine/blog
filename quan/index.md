# 量子信息与量子计算


<!--more-->

{{< admonition quote "课程信息" true >}}
🎓 数学科学学院<br>
🕙 2023-2024 秋冬<br>
🧑‍🏫 毕惟红<br>
📝 50%读书报告，10%考勤，10%编程，30%两次展示
{{< /admonition >}}

!!! quote ""
    - 🎓 数学科学学院
    - 🕙 2022-2023 秋冬
    - 🧑‍🏫 武俊德
    - 📝 签到，作业，课程论文

## 参考

- 讲义

## 课程论文 

!!! abstract "Decomposition of arbitrary unitary transformations in quantum computing"

    ### Abstract
    
    In order to achieve universal quantum computing in the way of classical computers, this paper focuses on the method of decomposing any Unitary transformation under n qubits into the most basic Hadamard gate, phase shift gate and CNOT gate, so that based on the physical construction of these three gates, most computing situations can be generally realized. We first demonstrate the decomposability of single Qubit gates based on Hadamard gates and phase shift gates, and consider the fact that dual Qubits gates can be constructed by CNOT gates, further verify that the Unitary transform under arbitrary n qubits can be decomposed into single Qubit gates and double Qubits gates, which provides a basis for discussing the physical implementation of quantum computers.
    
    ### Problem narrative
    
    #### Background
    
    We already know that in classical computing, all logical operations can be completed with only three operations, or and not, so as long as the physical construction of these three logic gates is realized, it lays the foundation for the implementation of general-purpose computers. Similarly, in quantum computing, for arbitrary quantum operations under n qubits, they are all Unitary variations due to the requirement of normalization, so the discussion of their universality can be equivalent to whether arbitrary unitary operations can be achieved by a combination of several elementary gates or approximated with arbitrary precision.
    
    #### Goal
    
    It is not an easy task to approximate the general unitary operation or find a set of quantum gates from the above propositions, so this paper is based on the electron spin quantum computing system with electron z-direction spin as the main measurement parameter, and takes the Hadamard gate, phase shift gate and CNOT gate as three basic gates, focusing on verifying the decomposition of any Unitary transform to the above three gates, so as to provide a basis for further discussion of general quantum computing.
    
    ### Gate decomposition of single qubit
    
    #### Operational equivalence
    
    We already know that Qubit's Unitary variation can be expressed in terms of a Unitary matrix. 
    
    According to the knowledge of abstract algebra and complex functions, due to
    
    $$U=e^{i\phi}SO_3,$$
    
    i.e. $U\sim SO_3.$
    
    That is, we can use one $SO_3$ matrix to describe it, and then any operation in Qubit is essentially an isometric transformation, that is, the rotation of the Bloch ball.
    
    #### Hadamard gate
    
    Based on the preceding hypothesis, we can define the basis vector of a quantum computing system as
    
    $$|0\rangle_z=(1,0)^T,|1\rangle_z=(0,1)^T.$$
    
    Then define the Hadamard gate as
    
    $$H=\displaystyle\frac{1}{\sqrt{2}}
    \left[\begin{array}{cc}
    1&1\\
    1&-1\\
    \end{array}\right]$$
    
    Because of $H^2=I,$ the Hadamard gate is unitary.
    
    Since the given quantum computing system works with the spin of the electron as a parameter, it can be seen that the base vector of the spin is the eigenstate of the electron spin in all directions, and after passing through the Hadamard gate, the resulting transformation is
    
    $$|0\rangle_x\rightarrow|0\rangle_z,|1\rangle_x\rightarrow |1\rangle_z,$$
    
    $$|0\rangle_y\rightarrow-|1\rangle_y,|1\rangle_y\rightarrow -|0\rangle_y,$$
    
    $$|0\rangle_z\rightarrow|0\rangle_x,|1\rangle_z\rightarrow |1\rangle_x.$$
    
    Thus, the Hadamard gate is essentially a turn of the Bloch ball around $(\displaystyle\frac{1}{\sqrt{2}},0,\displaystyle\frac{1}{\sqrt{2}})$ where $\delta=\pi$.
    
    #### Phase shift gate
    
    Define the Phase shift gate as 
    
    $$R_z(\delta)=
    \left[\begin{array}{cc}
    1&0\\
    0&e^{i\delta}\\
    \end{array}\right]$$
    
    It is essentially a rotation of the Bloch ball around the z-axis at a counterclockwise angle of $\delta$.
    
    #### Geometric validation of decomposition
    
    When we use the Hadamard gate, we can change the rotation on the z-axis provided by the Phase shift gate to the rotation on the x-axis; Similarly, the y-axis can be moved to the x-axis position with a Phase shift gate, and then the Hadamard gate and the Phase shift gate can be used to obtain the rotation of the y-axis.
    
    Next, by following the inference process of the Euler angle, a single point on the Bloch sphere can be moved to any position on the sphere, and the rigid body transformation $SO_3$ of the entire Bloch sphere can be further described. It is proved that only the Hadamard gate and the phase shift gate can complete any operation on a single Qubit, that is, a single Qubit gate can be successfully constructed.
    
    ### Gate decomposition of n qubits
    
    Since dual Qubits gates are controlled single qubits that can be constructed from CNOT gates, it is only necessary to verify that any Unitary transformation under n qubits can be decomposed into a combination of single Qubit gates and double Qubits gates.
    
    #### Construct a single controlled $C-U$ gate
    
    The core is that it has a control qubit, when controlling position 1, do the Unitary transformation $U$ for the operation bit, otherwise do not do the transformation.
    
    For a second-order unitary matrix acting on a single qubit
    
    $$U=\left[\begin{array}{cc}
    e^{i(\delta-\frac{\alpha}{2}-\frac{\beta}{2})}cos\frac{\theta}{2}&-e^{i(\delta-\frac{\alpha}{2}+\frac{\beta}{2})}sin\frac{\theta}{2}\\
    e^{i(\delta+\frac{\alpha}{2}-\frac{\beta}{2})}sin\frac{\theta}{2}&e^{i(\delta+\frac{\alpha}{2}+\frac{\beta}{2})}cos\frac{\theta}{2}\\
    \end{array}\right]$$
    
    by decomposition, we get
    
    $$U=\left[\begin{array}{cc}
    e^{i\delta}&0\\
    0&e^{i\delta}\\
    \end{array}\right]
    \left[\begin{array}{cc}
    e^{-i\frac{\alpha}{2}}&0\\
    0&e^{i\frac{\alpha}{2}}\\
    \end{array}\right]
    \left[\begin{array}{cc}
    cos\frac{\theta}{2}&-sin\frac{\theta}{2}\\
    sin\frac{\theta}{2}&cos\frac{\theta}{2}\\
    \end{array}\right]
    \left[\begin{array}{cc}
    e^{-i\frac{\beta}{2}}&0\\
    0&e^{i\frac{\beta}{2}}\\
    \end{array}\right]
    $$
    
    Note
    
    $$\Phi(\delta)=\left[\begin{array}{cc}
    e^{i\delta}&0\\
    0&e^{i\delta}\\
    \end{array}\right],
    R_z(\delta)=\left[\begin{array}{cc}
    e^{-i\frac{\delta}{2}}&0\\
    0&e^{i\frac{\delta}{2}}\\
    \end{array}\right],
    R_y(\delta)=\left[\begin{array}{cc}
    cos\frac{\delta}{2}&-sin\frac{\delta}{2}\\
    sin\frac{\delta}{2}&cos\frac{\delta}{2}\\
    \end{array}\right].$$
    
    and
    
    $$A=R_z(\alpha)R_y(\frac{\theta}{2}),B=R_y(-\frac{\theta}{2})R_z(-\frac{\alpha+\beta}{2}),C=R_z(\frac{\beta-\alpha}{2}).$$
    
    Then we know
    
    $$U=\Phi(\delta)A\sigma_x B\sigma_x C, I=ABC.$$
    
    \begin{figure}[h] 
    \centering
    \includegraphics[width=11cm]{fig1.png}
    \caption{Circuit diagram of $C-U$ gate} \label{fig1}
    \end{figure}
    
    From this, the $C-U$ gate can be constructed.
    
    #### Construct a multi-controlled $C^k-U$ gate
    
    Given $k\in \mathbb{N},k\ge2.$ Back to classical computers, we can construct Toffoli gates and use them to construct k-weight AND gates, similarly, here we need to construct a generality $C^2-U$ gate, and then we can further construct a multi-controlled $C^k-U$ gate to verify its feasibility.
    
    From algebraic knowledge, for any second-order unitary matrix $U$, after Jordan diagonalization and square, we can get the decomposition 
    
    $$U=V^2.$$
    
    Further, there is
    
    $$VV^{\dag}=I.$$
    
    \begin{figure}[h] 
    \centering
    \includegraphics[width=11cm]{fig2.png}
    \caption{Circuit diagram of $C^2-U$ gate} \label{fig2}
    \end{figure}
    
    So we get the $C^2-U$ gate that meets the requirements.
    
    #### General decomposition
    
    In order to extend the conclusion to any unitary transformation in n qubits, we need to verify that it can be implemented into two quantum states, that is, we only need to proof that
    
    $$U^{(2^n)}=\prod\limits_{i=1}^{2^n-1}\prod\limits_{j=0}^{i-1} V_{ij}.$$
    
    Since direct processing is difficult, we follow the process of proving odd and even arrangement in mathematics, swap quantum states one by one, and design the transformation gate shown in the figure, so that the exchange process is until the two quantum states to be transformed through the gate and then return to the original position in turn.
    
    \begin{figure}[h] 
    \centering
    \includegraphics[width=11cm]{fig3.png}
    \caption{Circuit diagram of swap gate} \label{fig3}
    \end{figure}
    
    Thus, we achieve the feasibility of the above operation, that is, the decomposition in the general case is also achievable.
    
    ### Further discussion of universal quantum computing implementation
    
    The proposition studied in this paper ultimately serves the universality of quantum computing. In fact, when we construct the $C^k-U$ gate, it has been proved that quantum computing can achieve universal classical computing, and the conclusion extension of general decomposition can be better applied to quantum simulation and special quantum computing, so as to meet the completeness of the conclusion in the case of quantum operations under n qubits.
    
    The interesting thing about the above work is that we can feel the inheritance of quantum computing to many theoretical ideas in classical computing. In the course of the author's study this semester, the course has been deeply involved in classical computing, so when it is introduced into the theory of quantum computing, many works have extensive similarities in the core, compared to the calculation itself, how to better prepare quantum states and better use the physical achievements of quantum mechanics is a more profound proposition left to us by this discipline.

[^1]: Unitary transformation (quantum mechanics). Detailed Pedia. https://
www.detailedpedia.com/wiki-Unitary_transformation_(quantum_mechanics)#

[^2]: Krol, A.M.; Sarkar, A.; Ashraf, I.; Al-Ars, Z.; Bertels, K. Efficient. 
Decomposition of Unitary Matrices in Quantum Circuit Compilers. Appl. Sci. 
2022, 12, 759.

[^3]: Mottonen, Mikko and Juha J. Vartiainen. “Decompositions of general 
quantum gates.” arXiv: Quantum Physics (2005): n. pag.

[^4]: Michael A. Nielsen, Isaac L. Chuang. Quantum Computation and Quantum 
Information. 

