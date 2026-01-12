在python中,希望实现多个进程之间的互斥,使用文件锁.
# 使用方法
```python
from filelock import FileLock
lock = FileLock(LOCK_FILE)
with lock:
    with open(DATA_FILE, "r", encoding="utf-8") as f:
        data = json.load(f)
    for item in data:
        if item["id"].endswith(uid):
            status = item.get("status", "todo")
            break
    else:
        raise RuntimeError("Concept not found")
```

# 实现原理
FileLock是在底层的数据结构中生成



# 参考
[[Alfred插件闪念捕捉实现]]