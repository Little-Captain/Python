# Python 解释器

## 环境变量

### PATH

* `Python` 所在的目录需要加入 `PATH` 路径。

### PYTHONHOME

* Python 安装目录，它必须包含一个 `lib` 子目录(包含 Python 标准库)。

### PYTHONPATH

* 一个目录列表。Python 可以从这些目录中导入模块。

* 这个`目录列表扩展了` Python 的 sys 模块的 `sys.path` 的值。

### PYTHONSTARTUP

* PYTHONSTARTUP 指定 `Python 启动时需要执行的代码`。

## 命令行语法和选项

* 总览

```bash
[path]python {options} [-c command | -m module | file | -] {args}
```

* `Python 常用命令行选项`

| 选项 | 含义 |
| :-: | :-: |
| `-B` | 不要将编译的字节码文件保存到磁盘 |
| `-c` | 指定 Python 语句(需要加引号)作为命令行的一部分 |
| `-E` | 忽略所有环境变量 |
| `-h` | 打印输出帮助文档 |
| `-i` | 在文件或命令运行后运行交互式会话 |
| `-m` | 指定要作为主脚本运行的 Python 模块或软件包 |
| `-O` | 优化生成的字节码 |
| `-OO` | 与 -O 类似，但要从字节码中删除文档字符串 |
| `-Q arg` | 控制除法运算符 / 在整数上的行为(仅 v2) |
| `-S` | 在启动时忽略隐式导入站点 |
| `-t` | 发出有关制表符(tab)用法不一致的警告(-tt 发出错误) |
| `-u` | 对标准输出和标准错误使用未缓冲的二进制文件 |
| `-v` | 详细跟踪模块的导入和清除操作 |
| `-V` | 打印 Python 版本号 |
| `-W arg` | 将一个条目添加到警告过滤器 |
| `-x` | 排除(跳过)主脚本源的第一行 |

## 交互式会话

* 在没有脚本参数的情况下运行 python，Python 会启动一个交互式会话并提示您输入 Python 语句或表达式。

* 在交互式环境中输入完整的语句时，Python 会执行它。输入完整的表达式时，Python 将对其进行评估。如果`表达式有结果`，Python 将`输出结果`，并`将结果分配给名为 _ 的变量`，以便您可以在另一个表达式中使用它。

* 当 Python 需要一个语句或表达式时，提示字符串为 >>>；`当语句或表达式已启动但尚未完成时，提示字符串为 ...`。

* 在 Windows 上键入 `Ctrl-C`，在类 Unix 系统上键入 `Ctrl-D`，`终止交互式会话`。语句抛出 SystemExit 也会终止会话，以交互方式或在运行的代码中调用 sys.exit() 也会终止会话。

* 可以免费下载其他替代的功能强大的交互环境。最受欢迎的是 `IPython`。 `bpython` 是一个更简单，更轻量但又非常方便的读行解释器。

## 运行 Python 程序

* 可以将 `Python 应用程序`视为`一组 Python 源文件`，它们是`普通的文本文件`。

* `脚本`是可以`直接运行`的文件。`模块`是可以`导入`的文件，以为其他文件或交互式会话提供功能。

* Python 文件既可以是模块(在导入时公开功能)，也可以是脚本(适合直接运行)。

* 一个有用且广泛使用约定是，`主要用于作为模块导入的 Python 文件`在`直接运行时`应执行一些简单的`自检`操作。

* Python 解释器会根据需要自动编译 Python 源文件。

* 在 `v2` 中，Python 将每个模块编译后的字节码文件保存在`与模块相同的目录`中，并具有相同的基本名称和扩展名 .pyc(在使用选项 -O 运行 Python 时为 .pyo)。

* 在 `v3` 中，Python 将已编译的字节码保存在包含模块源代码的目录的子目录 `__pycache__` 中，带有特定于版本的扩展名，并带有注释以表示优化级别。

* 使用 `-B 选项`运行 Python 以避免将已编译的字节码保存到磁盘，这在从只读磁盘导入模块时会很方便。

* `直接运行脚本时，Python 不会保存脚本的编译字节码形式`。Python 每次运行时都会重新编译脚本。

* `Python 仅为导入的模块保存字节码文件`。它会在必要时自动重建每个模块的字节码文件(例如，当您编辑模块的源代码时)。

* 根据不同的操作系统，可以直接从 `shell` 脚本或命令文件`调用 python`。

* 在类似 Unix 的系统上，可以通过设置文件的权限位 x 和 r 并使脚本以 shebang 行开头(`#!/usr/bin/env python`)来直接执行 Python 脚本，或以 `#!` 开头的行后跟 python 解释器程序的路径，在这种情况下，可以选择添加一个命令行选项(`#!/usr/bin/python -O`)

* 在 Windows 上，可以使用扩展名 `.pyw` 和解释程序 `pythonw.exe` 代替 .py 和 python.exe。

* 在 `Mac 上同理`，当要运行需要访问 GUI 工具包而不仅仅是文本模式交互的脚本时，需要使用解释程序 pythonw，而不是 python。

* `w 变体`在`没有文本模式控制台的情况下运行 Python`，因此`没有标准的输入和输出`。这些变体对于依赖 `GUI` 或在`后台隐形运行的脚本`很有用。

* 在`不需要调试程序时才使用 w 变体`，`在开发过程中需要保持标准输出和错误输出`可用于信息，警告和错误消息的输出。

## Jython 解释器

* Jython 解释器的运行方式`与 python 程序类似`。

```bash
[path]jython {options} [ -j jar | -c command | file | - ] {args}
```

* `-j` jar 告诉 Jython，要运行的主要脚本是 .jar 文件中的 `__run__.py`。

* 选项 `-i`，`-S` 和 `-v` 与 python 相同。`--help` 就像 python 的 -h，`--version` 就像 python 的 -V。

* Jython 在`安装目录`中使用一个名为 `registry` 的`文本文件`代替结构变量来`记录具有结构化名称的属性`(例如，属性 python.path 是 Jython 等效于 Python 的环境变量 PYTHONPATH)。可以使用 Jython 命令行选项以 `-D name = value` 的形式设置属性。

## IronPython 解释器

* IronPython 解释器的运行方式`与 python 程序类似`。

```bash
[path]ipy {options} [-c command | file | - ] {args}
```

## PyPy 解释器

* PyPy 解释器的运行方式`与 python 程序类似`。

```bash
[path]pypy {options} [-c command | file | - ] {args}
```
