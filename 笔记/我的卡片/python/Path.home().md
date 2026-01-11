# 功能
抽象出一个方法,以获取到当前系统中的用户目录.  
在windows下是:
```txt
C:\Users\yourname
```
在mac下是:
```txt
/Users/yourname
```


# 设计思路
通过抽象出一个Pat.home()方法,能够方便的适配底层不同的系统.提升代码的适应性.

# 用法
```python
Path.home() / "Documents" / "concepts.json"
```
这里的 /是转移符号,是获取当前目录下的子目录路径.
## 其他写法
```python
Path.home().joinpath("Documents", "concepts.json") 
```

这里是一个同样功能的写法.



# 参考
[[闪念捕捉]]