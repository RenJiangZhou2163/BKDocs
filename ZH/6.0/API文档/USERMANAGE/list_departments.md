
### 请求地址

/api/c/compapi/v2/usermanage/list_departments/



### 请求方法

GET


### 功能描述

获取部门列表

### 请求参数


#### 通用参数

| 字段 | 类型 | 必选 |  描述 |
|-----------|------------|--------|------------|
| bk_app_code  |  string    | 是 | 应用 ID     |
| bk_app_secret|  string    | 是 | 安全密钥(应用 TOKEN)，可以通过 蓝鲸智云开发者中心 -&gt; 点击应用 ID -&gt; 基本信息 获取 |
| bk_token     |  string    | 否 | 当前用户登录态，bk_token 与 bk_username 必须一个有效，bk_token 可以通过 Cookie 获取 |
| bk_username  |  string    | 否 | 当前用户用户名，应用免登录态验证白名单中的应用，用此字段指定当前用户 |


#### 接口参数

| 字段      |  类型      | 必须   |  描述      |
|-----------|------------|--------|------------| 
| lookup_field | 字符串 | 否 | 查找字段, 默认值为 'id' |
| page | 整数 | 否 | 页码 |
| no_page | 布尔 | 否 | 是否返回全部结果，默认为否 |
| page_size | 整数 | 否 | 每页结果数量 |
| fields | 字符串 | 否 | 返回值字段, 例如"username,id" |
| exact_lookups | 字符串 | 否 | 精确查找内容列表, 例如"jack,pony" |
| fuzzy_lookups | 字符串 | 否 | 模糊查找内容列表, 例如"jack,pony" |


### 请求参数示例 

``` json
{
  "fields": "name,id",
  "no_page": true
}
```

### 返回结果示例

```json
{
    "message": "Success",
    "code": 0,
    "data": [{
        "id": 4,
        "name": "PaaS",
    }],
    "result": true
}
```

### 返回结果参数说明

| 字段      | 类型     | 描述      |
|-----------|-----------|-----------|
|result| bool | 返回结果，true 为成功，false 为失败 |
|code|int|返回码，0 表示成功，其他值表示失败|
|message|string|错误信息|
|data| array| 结果 |