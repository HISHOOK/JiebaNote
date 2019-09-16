# jieba 0.39 注释版

本项目为jieba添加了注释，并结合自己的需要做了部分更改。主要更改内容如下： 

1、__init__.py  line44
```python
re_han_default = re.compile("([\u4E00-\u9FD5a-zA-Z0-9+#&\._%]+)", re.U)
```
改为
```python
re_han_default = re.compile("(.+)", re.U)
```
可以支持空格和特殊符号。
    
2、__init__.py  line133  
增加
```python
try:
    os.remove(cache_file)
except:
    pass
```
表示删除本地缓存jieba.cache文件，每次使用jieba都会重新建立缓存。

