# base58、base64编解码转换

## base58

### 安装

```
pip install base58
```

### base58编码

```
>>> import base58
>>> base58.b58encode(b'hello world')
b'StV1DL6CwTryKyV'
```

### base58编码(带校验和checksum)

```
>>> import base58
>>> base58.b58encode_check(b'hello world')
b'3vQB7B6MrGQZaxCuFg4oh'
```

### base58解码

```
>>> import base58
>>> base58.b58decode(b'StV1DL6CwTryKyV')
b'hello world'
```

### base58解码(带校验和checksum)

```
>>> import base58
>>> base58.b58decode_check(b'3vQB7B6MrGQZaxCuFg4oh')
b'hello world'
>>> base58.b58decode_check(b'3vQB7B6MrGQZaxCuFg4oH')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "/Users/revotu/dev/vee/env-vee/lib/python3.6/site-packages/base58.py", line 120, in b58decode_check
    raise ValueError("Invalid checksum")
ValueError: Invalid checksum
>>> 
```


## base64

### 安装

```
base64是内置库，无需安装
```

### base64编码

```
>>> import base64
>>> base64.b64encode(b'hello world')
b'aGVsbG8gd29ybGQ='
```

### base64解码

```
>>> import base64
>>> base64.b64decode(b'aGVsbG8gd29ybGQ=')
b'hello world'
```
