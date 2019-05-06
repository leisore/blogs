---
title: Thrift JSON协议
---

{{page.title}}

## JSON协议实现类
- TSimpleJSONProtocol：只是一个write-only实现，输出的JSON不是标准的JSON，输出格式适合脚本语言解析
- TJSONProtocol：实现中支持读写JSON，输出是标准的JSON

## 对于BOOL类型的处理
TSimpleJSONProtocol和TJSONProtocol在处理Bool类型，均把它们转换为整型的0和1处理。
- TSimpleJSONProtocol：
```
  public void writeBool(boolean b) throws TException {
    writeByte(b ? (byte)1 : (byte)0);
  }
```

- TJSONProtocol：
```
  @Override
  public void writeBool(boolean b) throws TException {
    writeJSONInteger(b ? (long)1 : (long)0);
  }
```

以上输出的JSON使用其他的JSON解析器解析的时候可能会出错。

{{ page.date|date_to_string }}