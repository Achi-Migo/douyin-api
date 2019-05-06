# 抖音签名服务

## 现已支持如下接口：

- [x] 签名服务接口调用次数
- [x] 搜索视频
- [x] 搜索用户
- [x] 获取热搜榜
- [x] 获取cookie
- [x]  获取主页推荐视频列表
- [x]  获取用户信息
- [x]  获取音乐信息
- [x]  获取用户喜欢的视频
- [x]  获取自己的视频
- [x]  获取评论信息
- [x]  获取粉丝列表
- [x]  获取关注列表


## 接口说明

### 1.获取使用次数

**请求方式：** GET(**HTTP**)

**请求地址：** [http://127.0.0.1:5000/douyin/get_call_count](http://127.0.0.1:5000/douyin/get_call_count)


**返回结果：**

    {
        "code":200,
        "data":{
            "total_count": xxx,
            "used_count": xxx
        }
        "msg":"请求成功"
    }

**参数说明：**

| 参数 | 说明 |
|:----|:-----|
|code|返回码 （200 为成功， 非200出错）|
|data|返回的数据体|
|total_count|总次数|
|used_count|已用次数|
|msg|对返回码的文本描述内容|

### 2.搜索视频

**请求方式：** GET(**HTTP**)

**请求地址：** [http://127.0.0.1:5000/douyin/search_video](http://127.0.0.1:5000/douyin/search_video)


**请求包体：** 

    {
        "keyword":"xxx",
        "cursor":"xxxx",
        "proxies":"xxx.xxx.xxx.xxx:xxx",
        "cookies":"{\"xxx\":"\xxx\"}"
    }
    
**请求示例**

[http://127.0.0.1:5000/douyin/search_video?keyword=美女&cursor=0](http://127.0.0.1:5000/douyin/search_video?keyword=美女&cursor=0)

**参数说明：**

| 参数 | 必须 | 说明 |
|:----|:---- |:-----|
|keyword|是|关键词|
|cursor|是|翻页的偏移量 每次叠加12， 默认0|
|proxies|否|代理ip|
|cookies|否|登陆后的cookie, json格式的字符串。不传则搜索成功率不高，可能返回空数据|

**返回结果：**

    {
        "code":200,
        "data":{
        }
        "msg":"请求成功"
    }

**参数说明：**

| 参数 | 说明 |
|:----|:-----|
|code|返回码 （200 为成功， 非200出错）|
|data|返回的数据体|
|msg|对返回码的文本描述内容|

### 3.搜索用户

**请求方式：** GET(**HTTP**)

**请求地址：** [http://127.0.0.1:5000/douyin/search_user](http://127.0.0.1:5000/douyin/search_user)


**请求包体：** 

    {
        "keyword":"xxx",
        "cursor":"xxxx",
        "proxies":"xxx.xxx.xxx.xxx:xxx",
        "cookies":"{\"xxx\":"\xxx\"}"
    }
    
**请求示例**

[http://127.0.0.1:5000/douyin/search_user?keyword=美女&cursor=0](http://127.0.0.1:5000/douyin/search_user?keyword=美女&cursor=0)

**参数说明：**

| 参数 | 必须 | 说明 |
|:----|:---- |:-----|
|keyword|是|关键词|
|cursor|是|翻页的偏移量 每次叠加20， 默认0|
|proxies|否|代理ip|
|cookies|否|登陆后的cookie，json格式的字符串。不传则搜索成功率不高，可能返回空数据|

**返回结果：**

    {
        "code":200,
        "data":{
        }
        "msg":"请求成功"
    }

**参数说明：**

| 参数 | 说明 |
|:----|:-----|
|code|返回码 （200 为成功， 非200出错）|
|data|返回的数据体|
|msg|对返回码的文本描述内容|

### 4. 获取热榜

**请求方式：** GET(**HTTP**)

**请求地址：** [http://127.0.0.1:5000/douyin/get_hot_search](http://127.0.0.1:5000/douyin/get_hot_search)

**请求包体：** 

    {
        "proxies":"xxx.xxx.xxx.xxx:xxx"
    }
    
**请求示例**

[http://127.0.0.1:5000/douyin/search_user?keyword=美女&cursor=0](http://127.0.0.1:5000/douyin/search_user?keyword=美女&cursor=0)

**参数说明：**

| 参数 | 必须 | 说明 |
|:----|:---- |:-----|
|proxies|否|代理ip|

**返回结果：**

    {
        "code":200,
        "data":{
        }
        "msg":"请求成功"
    }

**参数说明：**

| 参数 | 说明 |
|:----|:-----|
|code|返回码 （200 为成功， 非200出错）|
|data|返回的数据体|
|msg|对返回码的文本描述内容|

### 5. 获取cookie（非登陆cookie）

**请求方式：** GET(**HTTP**)

**请求地址：** [http://127.0.0.1:5000/douyin/get_cookies](http://127.0.0.1:5000/douyin/get_cookies)

**请求包体：** 

    {
        "proxies":"xxx.xxx.xxx.xxx:xxx"
    }
    
**参数说明：**

| 参数 | 必须 | 说明 |
|:----|:---- |:-----|
|proxies|否|代理ip|



**返回结果：**

    {
        "code":200,
        "data":{
        }
        "msg":"请求成功"
    }

**参数说明：**

| 参数 | 说明 |
|:----|:-----|
|code|返回码 （200 为成功， 非200出错）|
|data|返回的数据体|
|msg|对返回码的文本描述内容|


### 6.获取主页推荐视频列表

**请求方式：** GET(**HTTP**)

**请求地址：** [http://127.0.0.1:5000/douyin/get_feed_info](http://127.0.0.1:5000/douyin/get_feed_info)

**请求包体：** 

    {
        "proxies":"xxx.xxx.xxx.xxx:xxx"
    }
    
**参数说明：**

| 参数 | 必须 | 说明 |
|:----|:---- |:-----|
|proxies|否|代理ip|

**返回结果：**

    {
        "code":200,
        "data":{
        }
        "msg":"请求成功"
    }

**参数说明：**

| 参数 | 说明 |
|:----|:-----|
|code|返回码 （200 为成功， 非200出错）|
|data|返回的数据体|
|msg|对返回码的文本描述内容|

### 7.获取用户信息

**请求方式：** GET(**HTTP**)

**请求地址：** [http://127.0.0.1:5000/douyin/get_user_info](http://127.0.0.1:5000/douyin/get_user_info)


**请求包体：** 

    {
        "user_id":"xxx",
        "cookies":"{\"xxx\":"\xxx\"}",
        "proxies":"xxx.xxx.xxx.xxx:xxx"
    }
    
***请求示例**
    
[http://127.0.0.1:5000/douyin/get_user_info?user_id=107776778033&cookies={"odin_tt": "a124e10e85f7dc3b220202ff9d526c347314c2fadbd68d3d314b6ad7047dd71c064a9956bfc26e6edebcb58e8a5211b798303ad7cca243c50b00be5cce4b8814"}](http://127.0.0.1:5000/douyin/get_user_info?user_id=107776778033&cookies={"odin_tt": "a124e10e85f7dc3b220202ff9d526c347314c2fadbd68d3d314b6ad7047dd71c064a9956bfc26e6edebcb58e8a5211b798303ad7cca243c50b00be5cce4b8814"})
    
**参数说明：**

| 参数 | 必须 | 说明 |
|:----|:---- |:-----|
|user_id|是|用户id|
|cookies|是|非登陆的cookie，json格式的字符串|
|proxies|否|代理ip|

**返回结果：**

    {
        "code":200,
        "data":{
        }
        "msg":"请求成功"
    }

**参数说明：**

| 参数 | 说明 |
|:----|:-----|
|code|返回码 （200 为成功， 非200出错）|
|data|返回的数据体|
|msg|对返回码的文本描述内容|

### 8.获取音乐信息

**请求方式：** GET(**HTTP**)

**请求地址：** [http://127.0.0.1:5000/douyin/get_music_info](http://127.0.0.1:5000/douyin/get_music_info)


**请求包体：** 

    {
        "music_id":"xxx",
        "proxies":"xxx.xxx.xxx.xxx:xxx"
    }
    
**请求示例**

[http://127.0.0.1:5000/douyin/get_music_info?music_id=6674901603562277643](http://127.0.0.1:5000/douyin/get_music_info?music_id=6674901603562277643)

**参数说明：**

| 参数 | 必须 | 说明 |
|:----|:---- |:-----|
|music_id|是|音乐id|
|proxies|否|代理ip|

**返回结果：**

    {
        "code":200,
        "data":{
        }
        "msg":"请求成功"
    }

**参数说明：**

| 参数 | 说明 |
|:----|:-----|
|code|返回码 （200 为成功， 非200出错）|
|data|返回的数据体|
|msg|对返回码的文本描述内容|

### 9.获取用户喜欢的视频

**请求方式：** GET(**HTTP**)

**请求地址：** [http://127.0.0.1:5000/douyin/get_favorite_video_info](http://127.0.0.1:5000/douyin/get_favorite_video_info)


**请求包体：** 

    {
        "user_id":"xxx",
        "max_cursor":xxxx,
        "proxies":"xxx.xxx.xxx.xxx:xxx"
    }
    
**请求示例**

[http://127.0.0.1:5000/douyin/get_favorite_video_info?user_id=107776778033&max_cursor=0](http://127.0.0.1:5000/douyin/get_favorite_video_info?user_id=107776778033&cursor=0)

**参数说明：**

| 参数 | 必须 | 说明 |
|:----|:---- |:-----|
|user_id|是|用户id|
|max_cursor|是|第一页为0，翻页时为返回数据中的max_cursor|
|proxies|否|代理ip|

**返回结果：**

    {
        "code":200,
        "data":{
        }
        "msg":"请求成功"
    }

**参数说明：**

| 参数 | 说明 |
|:----|:-----|
|code|返回码 （200 为成功， 非200出错）|
|data|返回的数据体|
|msg|对返回码的文本描述内容|

### 10.获取自己的视频

**请求方式：** GET(**HTTP**)

**请求地址：** [http://127.0.0.1:5000/douyin/get_own_video_info](http://127.0.0.1:5000/douyin/get_own_video_info)


**请求包体：** 

    {
        "user_id":"xxx",
        "max_cursor":"xxxx",
        "proxies":"xxx.xxx.xxx.xxx:xxx"
    }
    
**请求示例**

[http://127.0.0.1:5000/douyin/get_own_video_info?user_id=107776778033&max_cursor=0](http://127.0.0.1:5000/douyin/get_own_video_info?user_id=107776778033&max_cursor=0)

**参数说明：**

| 参数 | 必须 | 说明 |
|:----|:---- |:-----|
|user_id|是|关键词|
|max_cursor|是| 第一页为0，翻页时为返回数据中的max_cursor|
|proxies|否|代理ip|

**返回结果：**

    {
        "code":200,
        "data":{
        }
        "msg":"请求成功"
    }

**参数说明：**

| 参数 | 说明 |
|:----|:-----|
|code|返回码 （200 为成功， 非200出错）|
|data|返回的数据体|
|msg|对返回码的文本描述内容|

### 11.获取评论信息

**请求方式：** GET(**HTTP**)

**请求地址：** [http://127.0.0.1:5000/douyin/get_comment_info](http://127.0.0.1:5000/douyin/get_comment_info)


**请求包体：** 

    {
        "aweme_id":"xxx",
        "cursor":"xxxx",
        "proxies":"xxx.xxx.xxx.xxx:xxx"
    }
    
**请求示例**

[http://127.0.0.1:5000/douyin/get_comment_info?aweme_id=6679382734034554126&cursor=0](http://127.0.0.1:5000/douyin/get_comment_info?aweme_id=6679382734034554126&cursor=0)

**参数说明：**

| 参数 | 必须 | 说明 |
|:----|:---- |:-----|
|aweme_id|是|视频id 如 6679382734034554126|
|cursor|是|翻页的偏移量 每次叠加20， 默认0|
|proxies|否|代理ip|

**返回结果：**

    {
        "code":200,
        "data":{
        }
        "msg":"请求成功"
    }

**参数说明：**

| 参数 | 说明 |
|:----|:-----|
|code|返回码 （200 为成功， 非200出错）|
|data|返回的数据体|
|msg|对返回码的文本描述内容|

### 12.获取粉丝列表

**请求方式：** GET(**HTTP**)

**请求地址：** [http://127.0.0.1:5000/douyin/get_follower_list](http://127.0.0.1:5000/douyin/get_follower_list)


**请求包体：** 

    {
        "user_id":"xxx",
        "max_time":"xxxx",
        "cookies":"{\"xxx\":"\xxx\"}",
        "proxies":"xxx.xxx.xxx.xxx:xxx"
    }
    
    
**请求示例**

http://127.0.0.1:5000/douyin/get_follower_list?user_id=107776778033&max_time=1556462749&cookies={"odin_tt":"a124e10e85f7dc3b220202ff9d526c347314c2fadbd68d3d314b6ad7047dd71c064a9956bfc26e6edebcb58e8a5211b798303ad7cca243c50b00be5cce4b8814"}


**参数说明：**

| 参数 | 必须 | 说明 |
|:----|:---- |:-----|
|user_id|是|用户id 如 107776778033|
|max_time|是|第一页为当前秒级时间戳，翻页时为返回数据中的min_time|
|cookies|是|非登陆的cookie，json格式的字符串|
|proxies|否|代理ip|

**返回结果：**

    {
        "code":200,
        "data":{
        }
        "msg":"请求成功"
    }

**参数说明：**

| 参数 | 说明 |
|:----|:-----|
|code|返回码 （200 为成功， 非200出错）|
|data|返回的数据体|
|msg|对返回码的文本描述内容|

### 13.获取关注列表

**请求方式：** GET(**HTTP**)

**请求地址：** [http://127.0.0.1:5000/douyin/get_following_list](http://127.0.0.1:5000/douyin/get_following_list)


**请求包体：** 

    {
        "user_id":"xxx",
        "max_time":"xxxx",
        "cookies":"{\"xxx\":"\xxx\"}",
        "proxies":"xxx.xxx.xxx.xxx:xxx"
    }
    
**请求示例**

http://127.0.0.1:5000/douyin/get_following_list?user_id=107776778033&max_time=1556462749&cookies={"odin_tt":"a124e10e85f7dc3b220202ff9d526c347314c2fadbd68d3d314b6ad7047dd71c064a9956bfc26e6edebcb58e8a5211b798303ad7cca243c50b00be5cce4b8814"}

**参数说明：**

| 参数 | 必须 | 说明 |
|:----|:---- |:-----|
|user_id|是|用户id 如 107776778033|
|max_time|是|第一页为当前秒级时间戳，翻页时为返回数据中的min_time|
|cookies|是|非登陆的cookie，json格式的字符串|
|proxies|否|代理ip|

**返回结果：**

    {
        "code":200,
        "data":{
        }
        "msg":"请求成功"
    }

**参数说明：**

| 参数 | 说明 |
|:----|:-----|
|code|返回码 （200 为成功， 非200出错）|
|data|返回的数据体|
|msg|对返回码的文本描述内容|




## 联系方式

**email**: bzkj@bzkj.tech

**wechat**: bzkj_tech
