```
python 的列表（List）是可以被改变的，这不像元组和字符串。
```

## 先产生一个List
```
list = [i for i in range(1,11)
print(list)
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

## List的方法
### :one: list.append(element)，把一个元素element添加到list的末尾
```python
list.append(11)
print(list)
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11]
```

### :two: list.extend(list1)，添加指定列表list1以扩充list
```python
list1 = [i*i for i in range(5,11)
print(list1)
[25, 36, 49, 64, 81, 100]
list.extend(list1)
print(list)
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 25, 36, 49, 64, 81, 100]
```

### :three: list.insert(i, element)，将元素element插到list指定索引i处
```python
list.insert(5, 666)
print(list)
[1, 2, 3, 4, 5, 666, 6, 7, 8, 9, 10, 11, 25, 36, 49, 64, 81, 100]
```

### :four: list.remove(element)，删除列表list中第一个值为element的元素
```python
list.remove(666)
print(list)
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 25, 36, 49, 64, 81, 100]
```

### :five: list.pop(i)移除列表list中指定索引i处的元素，并返回该元素；list.pop()移除list最后一个元素，并返回该元素
```python
list.pop(0)
print(list)
[2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 25, 36, 49, 64, 81, 100]
list.pop()
print(list)
[2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 25, 36, 49, 64, 81]
```

### :six: list.index(element)，返回list中值为element的第一个元素索引
```python
list.append(2)
print(list)
[2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 25, 36, 49, 64, 81, 2]
print(list.index(2))
0
```

### :seven: list.count(element)，统计元素element在list中出现的次数
```python
print(list.count(2))
2
```

### :eight: list.sort()，无参数默认对list进行升序排序，但可以传入参数list.sort(reverse=True)进行降序排序
```python
list.sort()
print(list)
[2, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 25, 36, 49, 64, 81]
list.sort(reverse=True)
print(list)
[81, 64, 49, 36, 25, 11, 10, 9, 8, 7, 6, 5, 4, 3, 2, 2]
```

### :nine: list.reverse()，反转list
```python
list.reverse()
print(list)
[2, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 25, 36, 49, 64, 81]
```

### :ten: list.copy，复制list对象list1=list.copy()，而不是单纯地如list1=list，否则一旦改变list1原来的list也会跟着变
```python
list1 = list.copy()
list2 = list
list2.remove(2)
print(list2,'\n',list,'\n',list1)
[2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 25, 36, 49, 64, 81]
[2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 25, 36, 49, 64, 81]
[2, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 25, 36, 49, 64, 81]
```
