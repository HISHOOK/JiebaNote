# jieba 0.39 注释版

本项目为jieba添加了注释，并结合自己的需要做了部分更改。主要更改内容如下： 

## 1、特殊字符
修改正则表达式使其可以支持空格和特殊符号（可以分出外国人名、书名等）。  
**修改位置：** 原__init__.py line44
```python
re_han_default = re.compile("([\u4E00-\u9FD5a-zA-Z0-9+#&\._%]+)", re.U)
```
改为
```python
re_han_default = re.compile("(.+)", re.U)
```

## 2、中文数字
增加正则匹配，提取中文数字。  
**修改位置：** 原__init__.py line281 cut主函数
```python
re_skip_chnum = 

```

## 3、本地缓存
表示删除本地缓存jieba.cache文件，每次使用jieba都会重新建立缓存。（根据代码缩写本身每次启动是会重新建立缓存的，但实际用时会出现不建立新缓存的情况）  
**修改位置：** 原__init__.py line133 
```python
try:
    os.remove(cache_file)
except:
    pass
```

## 配套博文
- [jieba源码解析（一）：分词之前](https://www.cnblogs.com/aloiswei/p/11507763.html)


