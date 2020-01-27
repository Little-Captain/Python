# Set 操作

* Python 提供了适用于 `Set`(`set` 和 `frozenset`) 的各种操作。

* 由于 Set 是`容器`，因此内置的 `len` 函数可以将集合作为其参数，并返回`集合的项数`。

* `Set` 是`可迭代对象`，因此 Set 可以`传递给`任何`接受可迭代对象参数`的`函数`或`方法`。在这时，迭代会以`任意顺序`产生 Set 的`项`(Set 无序)。

## 关系测试

* `k in S` 检查对象 k 是否为 Set S 的项。如果是返回 True，否则返回 False。`k not in S` 等价于 `not (k in S)`。

## Set 的方法

* Set 对象提供了多种方法如下表所示。不可变方法不改变其应用对象而返回结果(可以在 frozenset 实例上调用)。可变方法可能会更改其应用的对象(只能在 set 实例上调用)。

* 在下表中，S 表示任何 set 对象，S1 表示拥有可哈希项的可迭代对象(通常但不一定是 set 或 frozenset)，x 表示任何可哈希对象。

| 方法 | 描述 | 可变性(是否能改变 L) |
| :-: | :-: | :-: |
| S.copy() | 返回 S 的`浅拷贝`副本(该副本的`项`与 `S` 的`相同`，而不是其副本)，结果与 `set(S)` 一样 | 不可变 |
| S.difference(S1) | 返回所有`在 S 中`而`不在 S1 中`的项组成的 `Set` (`差集`) | 不可变 |
| S.intersection(S1) |  | 不可变 |
| S.issubset(S1) |  | 不可变 |
| S.issuperset(S1) |  | 不可变 |
| S.symmetric_difference(S1) |  | 不可变 |
| S.union(S1) |  | 不可变 |
| S.add(x) |  | 可变 |
| S.clear() |  | 可变 |
| S.discard(x) |  | 可变 |
| S.pop() |  | 可变 |
| S.remove(x) |  | 可变 |

Returns the set of all items of S that are also in S1

Returns True when all items of S are also in S1; otherwise, returns False

Returns True when all items of S1 are also in S; otherwise, returns False (like S1.issubset(S))

Returns the set of all items that are in either S or S1, but not both

Returns the set of all items that are in S, S1, or both

Adds x as an item to S; no effect if x was already an item in S

Removes all items from S, leaving S empty

Removes x as an item of S; no effect when x was not an item of S

Removes and returns an arbitrary item of S

Removes x as an item of S; raises a KeyError exception when x was not an item of S
