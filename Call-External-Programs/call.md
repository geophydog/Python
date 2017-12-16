:hotel: [Return to Home Page](https://github.com/geophydog/geophydog.github.io/blob/master/README.md)  
## 一 、调用SHELL

### 1.subprocess.call()
- __(1)__ 
```python
import subprocess
rc = subprocess.call(['ls -l'])
```
- __(2)__
```python
import subprocess
out = subprocess.call("ls -l", shell=True)
out = subprocess.call("cd ..", shell=True)
```
### 2. subprocess.Popen
#### __(1)__
```python
import subprocess
out = subprocess.Popen(["ls","-l"])
print("parent process")
```
#### __(2)__ 又如
```python
import subprocess
out = subprocess.Popen(["ping", "-c", "5", "www.google.com"])
print("Parent process")
```
    主程序开启子进程后并未等待child的完成， 而是直接执行print("Parent process")
    若要等待子进程完成，必须加上调用对象的wait()方法
    
```python
import subprocess
out = subprocess.Popen(["ping", "-c", "5", "www.google.com"])
out.wait()
print("Parent process")
```
#####  在父进程中对子进程进行其他操作
`- out.poll()     # 检查子进程状态 `  
`- out.kill()    # 终止子进程`  
`- out.send_signal() # 向子进程发送信号`  
`- out.terminate() # 终止子进程`  
`- out.pid  # 子进程pid`


### 3. 子进程文本操作
`沿用out子进程，其标准输入、输出与标准错误属性表示如下：`
``` python
out.stdin
out.stdout
out.stderr
```
- __我们可以在Popen()建立子进程的时候改变标准输入、标准输出和标准错误，  并可以利用subprocess.PIPE将多个子进程的输入和输出连接在一起，构成管道(pipe):__

``` python 
import subprocess
child1 = subprocess.Popen(["ls", "-l"], stdout=subprocess.PIPE)
child2 = subprocess.Popen(["wc", stdin=child1.stdout, stdout=subprocess.PIPE)
out = child2.communicate()
print(out)
```
- subprocess.PIPE实际上为文本流提供一个缓存区。child1的stdout将文本输出到缓存区，随后child2的stdin从该PIPE中将文本读取走。child2的输出文本也被存放在PIPE中，直到communicate()方法从PIPE中读取出PIPE中的文本。__要注意的是，communicate()是Popen对象的一个方法，该方法会阻塞父进程，直到子进程完成。__

- __我们还可以利用communicate()方法来使用PIPE给子进程输入:__
``` python
import subprocess
child = subprocess.Popen(["cat"], stdin=subprocess.PIPE)
child.communicate("vamei")
```
