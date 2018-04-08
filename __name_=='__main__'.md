:hotel:[Return to Python Home Page](https://github.com/geophydog/Python)

***

```
一个python的文件有两种使用的方法，第一是直接作为脚本执行，第二是import到其他的python脚本中被调用（模块重用）执行。
因此if __name__ == '__main__': 的作用就是控制这两种情况执行代码的过程.
在if __name__ == '__main__': 下的代码只有在第一种情况下（即文件作为脚本直接执行）才会被执行，而import到其他脚本中是不会被执行的。
```

__test1.py__
```python
print("I am A!")
if __name__ == '__main__':
   print("I am B!")
```

__output:__
```
I am A!
I am B!
```

```
如果test1.py作为test2.py的模块被导入，则test1.py的if __name__ == '__main__': 之后的代码不会被执行。
```
__test2.py__
```python
import test1
if __name__ == '__main__':
    print("I am C!")
```
