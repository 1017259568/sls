# DeleteIndex {#reference_ivq_pvz_c2b .reference}

为指定LogStore创建索引。

示例：

```
POST /logstores/{logstoreName}/index
```

## 请求语法 {#section_o54_dhh_f2b .section}

```
POST /logstores/<logstoreName>/index HTTP/1.1
Authorization: <AuthorizationString>
x-log-bodyrawsize: <x-log-bodyrawsize>
User-Agent: <User-Agent>
x-log-apiversion: <APIVersion>
Host: <Project Endpoint>
x-log-signaturemethod: hmac-sha1
Date: <GMT Date>
Content-Type: application/json
Content-MD5: <Content-MD5>
Content-Length: <Content-Length>
{
  "line": <full text index>,
  "keys": <key-value index>,
  "ttl": <ttl>
}
```

## 请求参数 {#section_lvh_2hh_f2b .section}

|**属性名称**|**类型**|**是否必须**|**描述**|
|:-------|:-----|:-------|:-----|
|logstoreName|string|是|Logstore 的名称。|
|ttl|integer|否|索引文件生命周期，支持7天，30天和90天。|
|keys|object|否|键值索引配置，key为字段名称，value为字段索引配置。|
|line|object|否|全文索引配置。|

属性keys和line必须至少指定一个。全文索引配置包含如下属性：

|**属性名称**|**类型**|**是否必须**|**描述**|
|:-------|:-----|:-------|:-----|
|caseSensitive|bool|否|是否大小写敏感。|
|chn|bool|否|是否包含中文。|
|token|array|是|分词符列表。|
|include\_keys|array|否|包含的字段列表。|
|exclude\_keys|array|否|排除的字段列表。|

字段索引配置包含如下属性：

|**属性名称**|**类型**|**是否必须**|**描述**|
|:-------|:-----|:-------|:-----|
|type|string|是|字段类型。|
|alias|string|否|字段别名。|
|chn|bool|否|是否包含中文，只有type为text时才有意义。|
|token|array|仅当type为text时必须|分词符列表，只有type为text时才有意义。|
|caseSensitive|bool|否|是否大小写敏感，只有type为text时有意义。|
|doc\_value|bool|否|该字段是否开启统计。|

**请求头**

CreateIndex接口无特有请求头，关于 Log Service API 的公共请求头请参考[公共请求头](cn.zh-CN/API 参考/公共请求头.md)。

**响应头**

CreateIndex接口无特有响应头，关于 Log Service API 的公共响应头请参考[公共响应头](cn.zh-CN/API 参考/公共响应头.md)。

**响应元素**

HTTP 状态码返回 200。

**错误码**

除了返回 Log Service API 的[通用错误码](cn.zh-CN/API 参考/通用错误码.md)，还可能返回如下特有错误码：

|**HTTP状态码**|**ErrorCode**|**ErrorMessage**|
|:----------|:------------|:---------------|
|400|IndexInfoInvalid|required field token is lacking or of error format|
|400|IndexAlreadyExist|log store index is already created|
|404|ProjectNotExist|The Project does not exist : \{Project\}|
|404|LogStoreNotExist|logstore \{logstoreName\} dose not exist|
|500|InternalServerError|Specified Server Error Message|

**说明：** 上表错误消息中 \{Project\} 和 \{logstoreName\} 表示该部分会被具体的 ProjectName 和 LogstoreName 来替换。**示例**

## 示例 {#section_p5z_ghh_f2b .section}

**请求示例：**

```
POST /logstores/my-logstore/index HTTP/1.1
Authorization: LOG LTRTfdR7fbosJYad:OK7Sldsxcv/8gz6YtrrmzR19Tgh=
x-log-bodyrawsize: 0
User-Agent: sls-java-sdk-v-0.6.1
x-log-apiversion: 0.6.0
Host: my-project.cn-shanghai.log.aliyuncs.com
x-log-signaturemethod: hmac-sha1
Date: Mon, 07 May 2018 09:43:16 GMT
Content-Type: application/json
Content-MD5: 22876515FC311F857AD6C7902F6A0148
Content-Length: 316
Connection: Keep-Alive
{
  "line": {
    "token": [
      ",",
      " ",
      "'",
      "\"",
      ";",
      "=",
      "(",
      ")",
      "[",
      "]",
      "{",
      "}",
      "?",
      "@",
      "&",
      "<",
      ">",
      "/",
      ":",
      "\n",
      "\t",
      "\r"
    ]
  },
  "keys": {
    "agent": {
      "doc_value": true,
      "caseSensitive": true,
      "alias": "agent_alias",
      "type": "text",
      "token": [
        ",",
        " ",
        "'",
        "\"",
        ";",
        "=",
        "(",
        ")",
        "[",
        "]",
        "{",
        "}",
        "?",
        "@",
        "&",
        "<",
        ">",
        "/",
        ":",
        "\n",
        "\t",
        "\r"
      ]
    }
  },
  "ttl": 90
}
```

**响应示例：**

```
HTTP/1.1 200
Server: nginx/1.12.1
Content-Length: 0
Connection: close
Access-Control-Allow-Origin: *
Date: Mon, 07 May 2018 09:43:16 GMT
x-log-requestid: 5AF01FB4826CF43228691C93
```

