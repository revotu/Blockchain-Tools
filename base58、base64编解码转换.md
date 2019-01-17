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

### base58解码

```
>>> import base58
>>> base58.b58decode(b'StV1DL6CwTryKyV')
b'hello world'
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
