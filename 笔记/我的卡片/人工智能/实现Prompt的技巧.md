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
你是一个文本处理大师
规则:
	必须将一个字符串翻转
	只返回翻转后的字符串
	不要返回标点符号,提示信息等其他信息
	不要返回输入信息
实例:
	输入 httpstatus 输出 sutatsptth
```

上面的俄en