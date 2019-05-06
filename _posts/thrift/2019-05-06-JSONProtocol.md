---
title: Thrift JSONЭ��
---

{{page.title}}

## JSONЭ��ʵ����
- TSimpleJSONProtocol��ֻ��һ��write-onlyʵ�֣������JSON���Ǳ�׼��JSON�������ʽ�ʺϽű����Խ���
- TJSONProtocol��ʵ����֧�ֶ�дJSON������Ǳ�׼��JSON

## ����BOOL���͵Ĵ���
TSimpleJSONProtocol��TJSONProtocol�ڴ���Bool���ͣ���������ת��Ϊ���͵�0��1����
- TSimpleJSONProtocol��
```
  public void writeBool(boolean b) throws TException {
    writeByte(b ? (byte)1 : (byte)0);
  }
```

- TJSONProtocol��
```
  @Override
  public void writeBool(boolean b) throws TException {
    writeJSONInteger(b ? (long)1 : (long)0);
  }
```

���������JSONʹ��������JSON������������ʱ����ܻ����

{{ page.date|date_to_string }}