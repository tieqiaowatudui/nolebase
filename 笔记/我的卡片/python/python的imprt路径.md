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

## 问题分析
- 当使用：
```bash
python week1/k_shot_prompting.py
```
运行时，Python 会将 **该 `.py` 文件所在的目录**（`demo_project/week1/`）作为 `sys.path[0]`。  
因此，Python 在遇到 `import llms` 时，会从 `week1/` 目录开始查找模块，但 `llms` 是平级目录，找不到，自然报错。
- `__init__.py` 的存在保证了 Python 将 `llms` 当作包来识别，这是 import 能成功的前提。
- 使用以下方式运行模块：
```bash
python -m week1.k_shot_prompting
```
时，Python 会将 **当前工作目录**（`demo_project/`）加入 `sys.path[0]`，并以包的方式加载模块。  
此时，`llms` 和 `week1` 成为同一搜索根下的平级包，因此可以被正常 import。
# 总结

- `ModuleNotFoundError` 的根本原因在于 **Python 模块搜索路径（sys.path）与运行方式的差异**。
- 使用 `python xxx.py` 时，搜索起点是 **脚本所在目录**；
- 使用 `python -m pkg.mod` 时，搜索起点是 **当前工作目录（pwd）**。
- 这是一个典型的 **“包级别运行 vs 脚本级别运行”** 差异问题。
- 因此，在涉及平级包的工程中，**推荐使用 `-m` 方式运行模块**，保证 import 正确。


