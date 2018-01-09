# api 接口文档
```
域名：http://127.0.0.1
端口：3000
```

## 目录：
### 用户模块
[1、用户登录](#1用户登录)<br/>
[2、用户登出](#2用户登出)<br/>
[3、添加用户](#3添加用户)<br/>
[4、更新用户权限](#4更新用户权限)<br/>
[5、删除用户](#5删除用户)<br/>
[6、更新用户密码](#6更新用户密码)<br/>
[7、用户列表](#7用户列表)<br/>
[8、根据uid查找用户详细信息](#8根据uid查找用户详细信息)<br/>

### 入库管理
[1、入库添加](#1入库添加)<br/>
[2、入库列表](#2入库列表)<br/>

### 出库管理
[1、出库添加](#1出库)<br/>
[2、出库列表](#2出库列表)<br/>

## 接口列表：

### 1、用户登录
#### 请求URL:  
```
/login
```

#### 请求方式: 
```
POST
```

#### 请求参数

|参数|是否必选|类型|说明|
|:-----|:-------:|:-----|:-----|
|username      |Y       |string  |用户名|
|password      |Y       |string  |密码|

#### 返回示例：

```javascript

```

### 2、用户登出
#### 请求URL:  
```
/outlogin
```

#### 请求方式: 
```
GET
```

#### 返回示例：

```javascript

```

### 3、添加用户
#### 请求URL:  
```
/user/add
```

#### 请求方式: 
```
POST
```

#### 请求参数

|参数|是否必选|类型|说明|
|:-----|:-------:|:-----|:-----|
|loginname      |Y       |string  |登录账号|
|username      |Y       |string  |用户名|
|state      |Y       |int  |权限（1普通用户/2管理员）|
|password      |Y       |string  |密码|

#### 返回示例：

```javascript

```

### 4、更新用户权限
#### 请求URL:  
```
/user/updatestate
```

#### 请求方式: 
```
POST
```

#### 请求参数

|参数|是否必选|类型|说明|
|:-----|:-------:|:-----|:-----|
|uid      |Y       |int  |用户id|
|state      |Y       |int  |权限（1普通用户/2管理员）|


#### 返回示例：

```javascript

```

### 5、删除用户
#### 请求URL:  
```
/user/delete
```

#### 请求方式: 
```
POST
```

#### 请求参数

|参数|是否必选|类型|说明|
|:-----|:-------:|:-----|:-----|
|uids      |Y       |数组  |用户id数组|

#### 返回示例：

```javascript

```

### 6、更新用户密码
#### 请求URL:  
```
/user/updatePassword
```

#### 请求方式: 
```
POST
```

#### 请求参数

|参数|是否必选|类型|说明|
|:-----|:-------:|:-----|:-----|
|oldpassword      |Y       |string |原密码|
|newpassword     |Y       |string |新密码|

#### 返回示例：

```javascript

```

### 7、用户列表
#### 请求URL:  
```
/user/list
```

#### 请求方式: 
```
GET
```

#### 请求参数

|参数|是否必选|类型|说明|
|:-----|:-------:|:-----|:-----|
|page      |N       |int|当前页数|
|limit     |N       |int  |每页显示条数|

#### 返回示例：

```javascript

```
### 8、根据uid查找用户详细信息

#### 请求URL:
```
/user/findone/:uid
```

#### 请求方式: 
```
GET
```

#### 请求参数

|参数|是否必选|类型|说明|
|:-----|:-------:|:-----|:-----|
|uid      |Y       |int|用户id|


#### 返回示例：

```javascript

```

### 1、入库添加

#### 请求URL:
```
/input/add
```

#### 请求方式: 
```
POST
```

#### 请求参数

|参数|是否必选|类型|说明|
|:-----|:-------:|:-----|:-----|
|com_cat     |Y       |int|入库类别（1/2）|
|onepeople   |Y       |string|经办人|
|twopeople     |Y       |string|保管员|
|datas     |Y       |数组|商品数据|

|参数|是否必选|类型|说明|
|:-----|:-------:|:-----|:-----|
|sname     |Y       |string|商品名称|
|size   |Y       |string|规格|
|price     |Y       |double|单价|
|unit     |Y       |string|单位|
|num     |Y       |int|数量|
|prices    |Y       |double|总价格|


#### 请求示例：

```javascript
{
        com_cat: 1,
        onepeople: "onepeople",
        twopeople: 'twopeople',
        datas: [
            {
                sname: "电视机",
                size: "海信T60",
                unit: "台",
                price: 6000,
                num: 2,
                prices: 12000
            },
            {
                sname: "中性笔",
                size: "齐心",
                unit: "支",
                price: 1.5,
                num: 100,
                prices: 150
            }
        ]
    }

```

### 2、入库列表

#### 请求URL:
```
/input/list
```

#### 请求方式: 
```
GET
```

#### 请求参数

|参数|是否必选|类型|说明|
|:-----|:-------:|:-----|:-----|
|page    |  N      |int|当前页数|
|llimt   |  N      |int|一页显示条数|


#### 返回示例：

```javascript

```

