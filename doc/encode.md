# encode

返回转码后的二进制字符串

```lua
function encode(format, data)
```

## Parameters
+ **format**

    **[in, string]** 编码类型.

+ **data**

    **[in, any]** 原始数据, 由编码类型确定参数类型

## Returns
+ **string**

  转码后的二进制字符串

+ **integer**

  已完成编码的原数据位置

## Remarks
编码类型:
  + `nil`

  返回所有的编码类型

  ```lua
    for k, v in pairs(encode()) do
      print(k);
    end
  ```
  + base64    
  + md5
  + hex
  + json
  + 字符编码

  ```lua
    io.stdout:write(encode('CP936', '阿斯蒂芬'))
  ```

## Requirements
  + json

    需要json模块支持

  + 字符编码

    需要`iconv.dll`基码组件


##  See Also
[decode](decode.md)
