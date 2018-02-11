## eoLinker-API Shop 
### 基于Python的IP地址查询API接口调用代码示例
#### 一、接口名称：IP地址查询
#### 二、接口描述：根据IP地址或者域名，查询该IP所属的区域
#### 三、接口平台：eoLinker-API Shop （apishop.net）

本代码示例是基于Python的eoLinker-API Shop **查询IP信息** API服务请求的代码示例，使用前你需要：

①：通过https://www.apishop.net/#/api/detail/?productID=118 申请API服务

**以下是完整代码示例：**
```
//post请求
#!/usr/bin/env python
# -*- coding: utf-8 -*-
# 测试环境: python2.7
# 安装requests依赖 => pip install requests/ easy_install requests

# 导入requests依赖
import requests
import json
import sys

reload(sys)
sys.setdefaultencoding("utf-8")
   '''
   转发请求到目的主机
   @param method str 请求方法
   @param url str 请求地址
   @param params dict 请求参数
   @param headers dict 请求头
   '''
   if method == "POST":
       return requests.post(url=url, data=params, headers=headers)
   elif method == "GET":
       return requests.get(url=url, params=params, headers=headers)
   else:
       return None

method = "POST"
url = "https://api.apishop.net/common/ip/queryIPInfo
headers = None
params = {
   apiKey : "参数1",
   ip : "参数2"
}
result = apishop_send_request(method=method, url=url, params=params, headers=headers)
if result:
   body = result.text
   response = json.loads(body)
   status_code = response["statusCode"]
   if (status_code == "000000"):
       # 状态码为000000, 说明请求成功
       print("请求成功：%s" % (body,))
   else:
       # 状态码非000000, 说明请求失败
       print("请求失败: %s" % (body,))
   else:
       # 返回内容异常，发送请求失败
       print("发送请求失败"")
 ```