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
FileLock在不同平台中使用了os的特性.在linux下使用了fctl/filelock.  
实现原理和通用的锁类似.
```txt
进程试图获取锁
如果锁空闲就获取锁,否则就被block在一个
```




# 参考
[[Alfred插件闪念捕捉实现]]