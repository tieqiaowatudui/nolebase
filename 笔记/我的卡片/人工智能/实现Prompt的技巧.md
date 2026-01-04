# 颠倒字符串
> 给定一个字符串,让大模型输出翻转后的字符串.不返回额外的其他字符串.

```python
"""
Reverse the order of letters in the following word. Only output the reversed word, no other text:

httpstatus
"""
```

# 用户提示方式
对于最低等级的 `google/gemma-2-2b-it`这种小模型,如果用一般的提示语实现就非常的苦难.
实现的方式是:
```c
YOUR_SYSTEM_PROMPT = """
 你是一个文本处理大师
规则:
	必须将一个字符串翻转
	只返回翻转后的字符串
	不要返回标点符号,提示信息等其他信息
	不要返回输入信息
	如果输入为 "httpstatus" 你必须准确输出 "sutatsptth"
"""
```

上面的内容最关键的是:
## 角色提示
提示大模型当前的角色
## 规则(Rules)
大模型对于`规则(Rules)`关键字非常敏感

### 必须
提示大模型必须要完成的工作.

### 只(Only)
提示大模型只完成对应的工作

### 不要(Not)
明确告知大模型必须静止干什么

### 如果....必须精确
举一个例子,告知大模型必须怎么干.这里是一个示例,这里避免了大模型进行模式化.

以上的所有的实现方式都是确定的.在一个di'dua
