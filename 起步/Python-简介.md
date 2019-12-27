# Python 简介

* Python 是龟叔(Guido van Rossum)于 `1990` 年开发的一门`通用目的`的编程语言。

## Python 语言

* `简单`

* `通用目的`

* `胶水语言`

* `更高级别的抽象`

* `开发效率高`

* `面向对象支持`

## Python 标准库和扩展模块

* `标准库`和`扩展模块`对于有效使用 Python 几乎和`语言本身`一样重要。

* Python 标准库提供了许多精心设计的`纯 Python 模块`，以方便重用。因为这些模块是用 Python 编写的，所以它们可以在 `Python 支持的所有平台`上工作。

* `未使用 Python 编码的扩展模块不一定具有`与纯 Python 代码相同的`跨平台可移植性`。

* 可以使用`低级语言编写特殊用途`的`扩展模块`，以使最初使用 Python 原型化的小型计算密集型部件获得`最高性能`。

* 可以使用 `Cython` 和 `CFFI` 之类的工具将现有的 C/C++ 库包装到 Python 扩展模块中

* 可以`将 Python 嵌入在其他语言中`，通过特定于应用程序的 Python 扩展模块将现有应用程序功能公开给 Python 脚本。

## Python 的一些实现

* Python 当前有四个`生产质量`的实现(CPython、Jython、IronPython、PyPy)

* 一个处于`早期开发阶段`的`新高性能`实现 Pyston

### CPython

* `Classic Python`(通常称为 Python) 是 Python 的`最新`，`最可靠`和完整的`生产质量`实现。

* CPython 是一个`编译器`，`解释器`，以及`一组内置和可选扩展模块`，`全部以标准 C 编码`。

* CPython 可以在 C 编译器符合 ISO/IEC 9899:1990 标准的任何平台(`几乎所有现代流行的平台`)上使用。

### Jython

* `Jython` 是适用于任何与 Java 7 或更高版本兼容的 Java 虚拟机(`JVM`)的 `Python 实现`。

* 当前(2019-12-27) Jython `支持 v2`，但`尚不支持 v3`。

* 通过 Jython，可以使用`所有 Java 库和框架`。

* 不必使用 Java 编码，但需要有 `Java 基础`。

### IronPython

* `IronPython` 是 Microsoft 为公共语言运行时(CLR)(通常称为 `.NET`)设计的的 `Python 实现`。

* 当前(2019-12-27) IronPython `支持 v2`，但`尚不支持 v3`。

* 现已开放源代码并移植到 `Linux` 和 `macOS`。

* 使用 IronPython，可以使用`所有 CLR 库和框架`。

* 不必使用 C# 编码，但需要有 `C# 基础`。

### PyPy

* `PyPy` 是 Python 的一种`快速`，`灵活`的实现，使用 Python 本身的一个子集进行编码。

* PyPy 的最大优势在于它能够`在运行 Python 程序时“及时”生成本机代码`。

* 当前(2019-12-27) PyPy 同时`支持 v2 和 v3`。

* PyPy 在`速度`和`内存管理`方面具有`显着优势`，并且正在生产级项目中使用。

### CPython、Jython、IronPython 和 PyPy 如何选择

* 这些实现之间的主要`区别`是它们的`运行环境`以及`可以使用的库和框架`不同。

#### CPython 的优势

* 主要在`传统环境`中工作，那么 CPython 非常适合。

* 如果您`不偏爱其中一种`，请从标准 CPython 参考实现开始。

* `CPython` 应用程序通常比 `Jython` 或 `IronPython` 更`快`，特别是使用扩展模块时。

* `CPython` 是`最成熟`的：已经存在了更长的时间，而 Jython，IronPython 和 PyPy 则较新。

* `CPython` 版本的`开发`趋向于`领先` Jython，IronPython 和 PyPy。

#### Jython 的优势

* `JVM 环境`下，Jython 是最佳选择。

* `Jython` 可以使用`任何Java类`作为扩展模块，无论该类来自标准 Java 库，第三方库还是您自己开发的库。

* `Jython` 编码的应用程序是 100% 纯 Java 应用程序，具有 `Java` 的所有`部署优势`和问题，并且可以在具有合适 JVM 的任何目标计算机上运行。

#### IronPython 的优势

* `CLR(.NET) 环境`下，请使用IronPython。

* `IronPython` 可以使用`任何 CLR 类`，无论是来自标准 CLR 库中的类，还是以 C#，Visual Basic .NET 或其他与 CLR 兼容的语言进行编码的类。

* `IronPython` 编码的应用程序完全`符合 .NET 的规范`。

#### PyPy 的优势

* 需要自定义版本的 Python，或者需要`高性能`的长期运行程序，请考虑使用 PyPy。

* 由于 PyPy 可以`实时编译机器代码`，因此 PyPy 通常`比 CPython 快`。

* PyPy 与大多数标准 CPython 库兼容。

### 其他

#### Pyjion

* `Pyjion` 是 `Microsoft` 的一个`开源项目`。

* `主要目标`是`向 CPython 添加 API 来管理 JIT 编译器`。

* `次要目标`是`为 Microsoft 的核心 CLR 环境创建 JIT 编译器`。

#### IPython

* Python 的`所有标准功能`都可用。

* IPython `增强了标准 CPython`，使其更强大，更`便于交互使用`。

* IPython 通过允许缩写的函数调用语法和百分号(%)字符的引入`扩展了解释器`的功能。

* IPython 提供了 `shell 转义`，从而`允许 Python 变量接收 shell 命令的结果`。

* 可以使用`问号查询对象的文档`(扩展文档使用两个问号)。

* IPython 在以`科学和数据`为中心的世界中取得了长足的进步，并逐渐变了一个交互式编程环境(`Jupyter Notebook`)，其中包括代码，还可以让您以文字编程风格嵌入注释，并显示执行代码的输出，以及由 matplotlib 和 bokeh 等子系统生成的高级图形。

#### MicroPython

* `MicroPython` 是一个 `Python 3 实现`，它`可以生成字节码或可执行的机器代码`。

* MicroPython `实现了 v3 的语法`，但是`缺少大多数标准库`。

* 有了 MicroPython，`Python` 语言才得以在物联网中扮演完整角色。

#### Anaconda 和 Miniconda

* 近年来`最成功`的 `Python 发行版`之一

#### Nuitka

* 将 `Python` 转换为 `C++`。

* Nuitka 是`一种编译器`，可将 Python 代码转换为 C++，并`支持 v2 和 v3`。

* Nuitka 可以方便地`优化代码`，`速度更快`，当前`速度是 CPython 的两倍`。

#### Grumpy

* Grumpy 是一个实验性的编译器，可将 `Python` 代码转换为 `Go`，仅支持 `v2`。

#### Transcrypt

* 将 `Python` 转换为 `JavaScript`。

## Python 的版本版本

* `Pytyon 2` 永远不会有 `2.8 版本`，建议使用 `Python 3`。

* `Python 3` 是一个主要发行版，`打破了`与 Python 2 的`兼容性`。

## 安装 CPython

* `建议`使用预构建的`二进制发行版`安装。

* 如果平台`预装了 Python`，则仍然`建议`安装另一个`独立`的`最新版本`。

* 通过`源代码`进行安装可以为您提供更多的`控制`和`灵活性`。

* 如果`找不到`适合您平台的预构建`二进制发行版`，则`必须`通过`源码`进行`安装`。

### 从二进制安装

* 通过 Python `官网下载`需要的`二进制发行版`，然后`按步骤安装`即可

### 从源码安装

* 要从源代码安装 CPython，您`需要`一个平台，该`平台带有符合 ISO 的 C 编译器`和诸如 `make 之类的工具`。

* 在 `Windows` 上，构建 Python 的常规方法是使用 `Visual Studio`(对于 v2，最好是 VS2008 和 VS2010，对于 v3，最好是 VS 2015)。

## 安装 Jython

* 请访问 Jython 主页，下载 Jython。 按照安装说明执行安装即可。

## 安装 IronPython

* 要安装 IronPython，需要在计算机上安装`公共语言运行时(CLR)`实现。

* IronPython 在 `Mono` 和 `Microsoft .NET Framework` 下都可以正常工作。

* 请访问 IronPython 主页，下载 IronPython。 按照安装说明执行安装即可。

## 安装 PyPy

* 请访问 PyPy 主页，按照需要选择下载安装。
