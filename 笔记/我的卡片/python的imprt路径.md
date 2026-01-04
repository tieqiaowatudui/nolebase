在写python的时候,经常会遇到import的问题.最近发现了一个错误是:
> ModuleNotFoundError: No module named 'llms'

# 问题描述
## 工程结构
```c
demo_project/
├── llms/
│   ├── __init__.py
│   └── chat.py
├── week1/
│   └── k_shot_prompting.py

```

然后我在chat.py文件中定义了cht函数:
```python
def chat():
    print("hello from llms.chat")

```

 week1/k_shot_prompting.py

```python
from llms import chat

chat()

```

在 **`demo_project/` 目录下**运行：
```bash
python week1/k_shot_prompting.py
```
结果就报错了:
```bash
Traceback (most recent call last):
  File "week1/k_shot_prompting.py", line 1, in <module>
    from llms import chat
ModuleNotFoundError: No module named 'llms'

```

这里涉及到的情况是:
```bash
python week1/k_shot_prompting.py
```
这种指令执行的时候,`sys.path[0]`指向了 `demo_project/week1/`目录下.那么python执行的会后,遇到了import的时候会在`sys.path[0]`目录开始往下查找,这个时候就无法找到对应的model了.
对于这种情况.使用python -m w




