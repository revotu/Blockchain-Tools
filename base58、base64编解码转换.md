# base58、base64等常见编解码转换

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
>>> base58.b58decode_check(b'3vQB7B6MrGQZaxCuFg4oH')            #  校验和验证不通过，则报错
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "/Users/bin/python3.6/site-packages/base58.py", line 120, in b58decode_check
    raise ValueError("Invalid checksum")
ValueError: Invalid checksum
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


## binascii

### 安装

```
binascii是内置库，无需安装
```

### 十六进制字符串转字节（hex -> bytes）

```
>>> import binascii
>>> binascii.a2b_hex('000102030405060708090a0b0c0d0e0f')
b'\x00\x01\x02\x03\x04\x05\x06\x07\x08\t\n\x0b\x0c\r\x0e\x0f'
>>> binascii.a2b_hex(b'000102030405060708090a0b0c0d0e0f')
b'\x00\x01\x02\x03\x04\x05\x06\x07\x08\t\n\x0b\x0c\r\x0e\x0f'
```


### 字节转十六进制字符串（bytes -> hex）

```
>>> binascii.b2a_hex(b'\x00\x01\x02\x03\x04\x05\x06\x07\x08\t\n\x0b\x0c\r\x0e\x0f')
b'000102030405060708090a0b0c0d0e0f'
>>> binascii.b2a_hex(b'\x00\x01\x02\x03\x04\x05\x06\x07\x08\t\n\x0b\x0c\r\x0e\x0f').decode('utf8')
'000102030405060708090a0b0c0d0e0f'
```
