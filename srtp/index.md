# Matlab 曲线拟合工具箱 SRTP


<!--more-->

## 开发日志

### 2023.5.26

- 在函数说明文档中提供了`spapi`的部分具体实现方式

### 2023.5.23

- 对部分函数进行了单增排列和参数检查上的功能优化

### 2023.5.18 会议记录

- `ba_obj` 中存放一个 `void *` 类型的指针，这种类型的指针可以被转化为任意类型的指针，用来指向其保存的数据的内存位置
  - 在构造 `ba_obj` 对象的时候传给其构造函数的指针尽量指向堆内存
  - 若要指向栈内存，对象的生命周期需要开发者自行维护。
  - 注：若使用栈内存构造一个 `ba_obj` 对象，在离开当前作用域之后该 `ba_obj` 对象仍被使用，则其内部指针指向的数据其实已经被释放，此时很可能会引发软件闪退问题
- `ba_obj` 的设计初衷是用来保存和传递矩阵的，不要对 `ba_obj` 对象写下 `get< int / double >()`
- `ba_obj` 的构造函数的参数中的指针参数也应该指向堆内存
- `ba_obj` 不需要指针参数的构造函数内部也是重新 `new` 了堆内存赋值给其保存的指针的
- 软件中的 `int,double` 被视为 $1 \times 1$ 的 `int,double` 矩阵，不存在C++中独立的 `int,double`
- `baltam::structure` 中保存一个 `std::map<std::string, ba_obj_ptr>` 作为存储数据的数据结构
  - 其 `map` 的 `value` 是指向 `ba_obj` 的智能指针
  - 在给 `baltam::structure` 使用 `set_field(key,value_ptr)` 函数添加字段 `key` 的时候，数据指针`value_ptr` 应指向堆内存

- 测试脚本的两个目的
  - 给不熟悉相关理论的用户一个快速上手的示例
  - 测试函数的功能

- 对于错误输入的处理并不一定要与MATLAB相同，可以更多的考虑相关理论的背景，报错与否一个重要的考量是用户友好

### 2023.5.16

- 改写并优化了`fnval`和`fnder`的测试脚本

### 2023.5.13

- 新增`spapi`函数说明

### 2023.5.9

- 新增测试 `test_fnval.m` 和 `test_fnder.m`

### 2023.4.24

- 优化了函数说明文档，统一了表达方式和字体样式
- 更正了`fnder`和`ppmak`文档中的错误表述

### 2023.4.12 会议记录

- 介绍开发环境与插件的机制及开发规范，具体可见
  [C++ 开发规范](http://183.66.214.98:20005/numerical_computation/style_guide/-/wikis/C++-%E5%BC%80%E5%8F%91%E8%A7%84%E8%8C%83)
  [mac操作系统使用安装北太天元](https://www.bilibili.com/video/BV1SW4y1j71Y/?spm_id_from=333.999.0.0&vd_source=ee756967a7f488a76fc48a6117203f55)
- 内核的使用文档，具体可见 `spline/deps/core/share/doc/html`
- 报bug的方式：在gitlab中的议题中报
- 介绍源码的调试方法，文档可见 
  [CLion调试baltam依赖的动态库](http://183.66.214.98:20005/numerical_computation/style_guide/-/wikis/CLion%E8%B0%83%E8%AF%95baltam%E4%BE%9D%E8%B5%96%E7%9A%84%E5%8A%A8%E6%80%81%E5%BA%93)
- 讲解test测试脚本的书写和保留及函数说明文档的书写

### 2023.4.9

- 在`.gitignore`新增了对部分开发环境下冗余文件的忽略

### 2023.4.7

- 新增 `fn2fm` 函数功能 `ns = fn2fm(s,form)`的使用文档
- 新增 `fnder` 函数功能 `ds = fnder(s,order)`的使用文档
