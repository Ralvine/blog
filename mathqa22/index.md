# 


# 高等数学答疑

!!! info "2022-12-21"
    ## Problem 1.

    (提示) 由古典概型，计算概率时，分母为所给字母的全排列，分子为限定条件的所有可能情况。

    1. $P=\frac{A_{10}^{10}}{A_{11}^{11}}=\frac{1}{11}$.

    2. $P=\frac{2\times A_{10}^{10}}{A_{11}^{11}}=\frac{2}{11}$.

    ## Problem 2.

    (提示) 先对首行进行展开，观察所得再分别对$d_n$,$c_n$所处行或列进行展开即可。

    $$\begin{array}{ll}
    D_{n}&\xlongequal[]{\text{按首行展开}}
    a_n \left|\begin{array}{ccccccc}
    a_{n-1}&&&&&b_{n-1}&0\\
    &\ddots&&&\iddots&&\\
    &&a_1&b_1&&&\\
    &&c_1&d_1&&&\\
    &\iddots&&&\ddots&&\\
    c_{n-1}&&&&&d_{n-1}&\\
    0&&&&&&d_n\\
    \end{array}\right|
    +b_n(-1)^{1+2n} \left|\begin{array}{ccccccc}
    0&a_{n-1}&&&&&b_{n-1}\\
    &&\ddots&&&\iddots&\\
    &&&a_1&b_1&&\\
    &&&c_1&d_1&&\\
    &&\iddots&&&\ddots&\\
    &c_{n-1}&&&&&d_{n-1}\\
    c_n&&&&&&0\\
    \end{array}\right|
    \\
    &=a_n d_n \left|\begin{array}{cccccc}
    a_{n-1}&&&&&b_{n-1}\\
    &\ddots&&&\iddots&\\
    &&a_1&b_1&&\\
    &&c_1&d_1&&\\
    &\iddots&&&\ddots&\\
    c_{n-1}&&&&&d_{n-1}\\
    \end{array}\right|
    -b_n c_n \left|\begin{array}{cccccc}
    a_{n-1}&&&&&b_{n-1}\\
    &\ddots&&&\iddots&\\
    &&a_1&b_1&&\\
    &&c_1&d_1&&\\
    &\iddots&&&\ddots&\\
    c_{n-1}&&&&&d_{n-1}\\
    \end{array}\right|
    \\
    &=(a_n d_n-b_n c_n)D_{2(n-1)}\\
    &=(a_n d_n-b_n c_n)(a_{n-1}d_{n-1}-b_{n-1}c{n-1})D_{2(n-2)}\\
    &\xlongequal[]{\text{以此类推}}(a_n d_n-b_n c_n)(a_{n-1}d_{n-1}-b_{n-1}c{n-1})\cdots(a_1 d_1-b_1 c_1)\\
    &=\displaystyle\prod_{i=1}^n (a_i d_i-b_i c_i)\\
    \end{array}$$

    ## Problem 3.

    $$\begin{array}{rl}
    AXC+XC&=A+2E\\
    \Rightarrow AXC+EXC&=A+2E\\
    \Rightarrow (A+E)XC&=A+2E\\
    \Rightarrow X&=(A+E)^{-1}(A+2E)C^{-1}\\
    &=\left(\begin{array}{ccc}
    -1&\frac{4}{3}&-\frac{2}{3}\\
    0&\frac{2}{3}&-\frac{4}{3}\\
    -2&\frac{5}{3}&-\frac{7}{3}\\
    \end{array}\right).\\
    \end{array}
    $$
    ## Problem 4.

    记$E_n$为单位矩阵，于是有

    $$\begin{array}{ll}
    r(A)+r(B)&=r(\left(\begin{array}{cc}
    A&O\\
    O&B\\
    \end{array}\right))\\
    &\le r(\left(\begin{array}{cc}
    A&O\\
    E_n&B\\
    \end{array}\right))\\
    \end{array}
    $$

    又因为

    $$\begin{array}{ll}
    \left(\begin{array}{cc}
    E_n&-A\\
    O&E_n\\
    \end{array}\right)
    \left(\begin{array}{cc}
    A&O\\
    E_n&B\\
    \end{array}\right)
    \left(\begin{array}{cc}
    E_n&-B\\
    O&E_n\\
    \end{array}\right)
    &=\left(\begin{array}{cc}
    O&-AB\\
    E_n&B\\
    \end{array}\right)
    \left(\begin{array}{cc}
    E_n&-B\\
    O&E_n\\
    \end{array}\right)\\
    &=\left(\begin{array}{cc}
    O&-AB\\
    E_n&O\\
    \end{array}\right)\\
    \end{array}
    $$
    因此

    $$\begin{array}{ll}
    r(A)+r(B)&\le r(\left(\begin{array}{cc}
    O&-AB\\
    E_n&O\\
    \end{array}\right))\\
    &=r(AB)+r(E_n)\\
    &=r(AB)+n\\
    \end{array}
    $$

    即

    $$r(AB)\ge r(A)+r(B)-n$$

    ## Problem 5.

    (提示) 分子为恰有两件次品的事件，即等价于从5件次品中取2件并从95件良品中取48件。

    $$\begin{array}{rl}
    P&=\frac{C_5^2\times C_{95}^{48}}{C_{100}^{50}}\\
    &=\frac{6125}{19206}\\
    \end{array}$$

    ## Problem 6.

    (提示) 类似地，对第一次取出旧球的数目进行讨论，计算各种情况下的概率并累加；第二小问中，由于第一次取球情况不受第二次取球的影响，直接计算即可。

    1. $$\begin{array}{rl}
    P&=\frac{C_3^3}{C_{12}^3}\times \frac{C_9^3}{C_{12}^3}+\frac{C_3^2 C_9^1}{C_{12}^3}\times \frac{C_8^3}{C_{12}^3}+\frac{C_3^1 C_9^2}{C_{12}^3}\times \frac{C_7^3}{C_{12}^3}+\frac{C_9^3}{C_{12}^3}\times \frac{C_6^3}{C_{12}^3}\\
    &=\frac{441}{3025}\\
    \end{array}$$

    2. $$\begin{array}{rl}
    P&=\frac{C_4^2}{C_6^2}\\
    &=0.4\\
    \end{array}$$

    ## Problem 7.

    (提示) 从对立事件入手。

    1. $$\bigcap_{i=1}^{10} A_i$$

    2. $$\overline{\bigcap_{i=1}^{10} A_i}$$

    3. 为便于表示，不妨记$D={1,2,\cdots,10}$，于是可表示为“只做对一道或全做错”的对立事件

    $$\overline{(\bigcup_{i=1}^{10}(A_i\cap (\bigcap_{j=D\textbackslash i} \overline{A_j})))\cup(\bigcap_{i=1}^{10} \overline{A_i})}$$


