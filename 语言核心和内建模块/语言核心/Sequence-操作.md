# Sequence 操作

* Python 支持适用于所有`序列`(包括字符串，列表和元组)的`各种操作`。

* `一些`序列操作`适用`于`所有容器`(包括不是序列的集合和字典)。

* `一些`序列操作`适用`于`所有可迭代对象`(`可循环`遍历的任何对象；所有`容器`，无论它们是否为序列，都是可迭代的；许多`不是容器的对象`也是可迭代的，如`生成器`对象)。

* 在本文中，需要非常`精确`地`使用`术语“`序列`”，“`容器`”和“`可迭代`”，以准确`指示`哪些`操作`适用于哪个`类别`。

## 一般 Sequence

* 序列是`有序容器`，其中包含可通过`索引`和`切片`访问的项。

* 内置的 `len` 函数将任何容器作为参数，并返回该容器中`项`的`个数`。

* 内置的 `min` 和 `max` 函数采用一个参数(一个非空的可迭代对象，其中的项是可比较的)，并分别返回`最小项`和`最大项`。

* 使用`多`个`参数`调用 `min` 和 `max`，在这种情况下，它们分别返回`最小参数`和`最大参数`。

* 内置的 `sum` 函数采用一个参数(一个可迭代对象，其中的项为数字)，并返回`数字`的`总和`。

### Sequence 转换

* 在不同的`序列`类型之间`没有隐式转换`(仅在 `v2` 中，Python 会`根据需要`将`字节字符串`转换为 `Unicode 字符串`)。

* 可以使用`单个参数`(任何`可迭代对象`)调用内置 `tuple` 和 `list`，来获取调用类型的`新实例`(`项`及其`顺序`与参数`保持一致`)。

### 连接与重复

* `+`: 可以`连接`相同类型的序列。

* `*`: `重复`连接序列指定的次数。

* `S * n` 或 `n * S` 是 S 的 `n 个副本`的`连接`。当 `n <= 0` 时，S * n 的结果是与 `S 类型相同`的`空序列`。

```python
# +
[1, 2] + [3] # [1, 2, 3]
# *
[1, 2] * 3 # [1, 2, 1, 2, 1, 2]
3 * [1, 2] # [1, 2, 1, 2, 1, 2]
[1, 2] * 0 # []
[1, 2] * -1 # []
```

### 测试关系

The x in S operator tests to check whether object x equals any item in the sequence (or other kind of container or iterable) S. It returns True when it does and False when it doesn’t. The x not in S operator is equivalent to not (x in S). For dictionaries, x in S tests for the presence of x as a key. In the specific case of strings, though, x in S is more widely applicable; in this case, x in S tests whether x equals any substring of S, not just any single character.

### 索引访问序列

To denote the nth item of a sequence S, use an indexing: S[n]. Indexing is zerobased (S’s first item is S[0]). If S has L items, the index n may be 0, 1…up to and including L-1, but no larger. n may also be -1, -2…down to and including -L, but no smaller. A negative n (e.g., -1) denotes the same item in S as L+n (e.g., L + -1) does. In other words, S[-1], like S[L-1], is the last element of S, S[-2] is the nextto- last one, and so on.
Using an index >=L or <-L raises an exception. Assigning to an item with an invalid index also raises an exception. You can add elements to a list, but to do so you assign to a slice, not an item, as we’ll discuss shortly.

### 切片访问序列

To indicate a subsequence of S, you can use a slicing, with the syntax S[i:j], where i and j are integers. S[i:j] is the subsequence of S from the ith item, included, to the jth item, excluded. In Python, ranges always include the lower bound and exclude the upper bound. A slice is an empty subsequence when j is less than or equal to i, or when i is greater than or equal to L, the length of S. You can omit i when it is equal to 0, so that the slice begins from the start of S. You can omit j when it is greater than or equal to L, so that the slice extends all the way to the end of S. You can even omit both indices, to mean a shallow copy of the entire sequence: S[:]. Either or both indices may be less than 0.
A negative index n in a slicing indicates the same spot in S as L+n, just like it does in an indexing. An index greater than or equal to L means the end of S, while a negative index less than or equal to -L means the start of S. Slicing can use the extended syntax S[i:j:k]. k is the stride of the slice, meaning the distance between successive indices. S[i:j] is equivalent to S[i:j:1], S[::2] is the subsequence of S that includes all items that have an even index in S, and S[::-1]5 has the same items as S, but in reverse order. With a negative stride, in order to have a nonempty slice, the second (“stop”) index needs to be smaller than the first (“start”) one—the reverse of the condition that must hold when the stride is positive. A stride of 0 raises an exception.

## 字符串(String)

## 元组(Tuple)

## 列表(List)
