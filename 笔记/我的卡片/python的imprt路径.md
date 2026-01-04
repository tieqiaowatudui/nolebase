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

### `week1/k_shot_prompting.py`

`from llms import chat  chat()`