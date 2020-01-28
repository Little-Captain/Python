# Dictionary 操作

* Python 提供了`多种`适用于`字典`的`操作`。

* 由于`字典`是`容器`，因此内置的 `len` 函数可以将字典作为其参数，并`返回`字典中的`项`(`键值对`)`数`。

* `字典`是`可迭代对象的`，因此可以将其传递给任何带有可迭代对象参数的函数。

* `迭代时`，以任意顺序`产出`字典的 `key`。 如，对于任何字典 D，`min(D)` 返回 D 中`最小`的 `key`。

New in 3.6: dictionaries have been reimplemented; keys are now iterated in insertion order until the first noninsertion mutator on the dict. To keep your code solid, do not rely on this new, nonguaranteed behavior until Python’s official docs explicitly ensure it.

* 3.6的新功能：重新实现了字典； 现在，按插入顺序迭代键，直到字典上的第一个非插入变量。 为了保持代码的稳定性，在Python的官方文档明确确认之前，请不要依赖这种新的，没有保证的行为。

## 关系测试

* `k in D` 检查`对象 k` 是否为`字典 D` 中的 `key`。如果 `k` `是` `D` 中的 `key`，返回 `True`，`否`则返回 `False`。`k not in D` 等价于 `not (k in D)`。

## 索引访问 Dictionary

## Dictionary 的方法
