# C++笔试


<!--more-->

- 输入输出
    - 带空格 getline
    - 字符串处理 string
    - 大小写转换
        - string: algorithm transform(str.begin(),str.end(),str.begin(),::tolower);
        - char: -'a'+'A'
    - 进制转换
        - bitset
        - 8(oct), 10(dec), 16(hex), 2(bitset(num))
    - 取整 (int)直接去除小数点后的部分
- 排序 sort 默认升序 自定义规则
    - functional greater<Type>
- 质数 因数分解
    - 时间复杂度 先判断n不是素数再进入计算循环
    - 分解到sqrt(n) 剩下的留n即可
