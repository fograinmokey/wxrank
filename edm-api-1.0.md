+ 2018年12月10日
     + API初始化
     
## 邮件管理-邮箱账户
+ Data
    + id (Long) - ID
    + email (String) - email账户
    + lastName (String) - 姓氏
    + name (String)     - 名字
    + positionalTitles (String) - 职称
    + emailCompany (String) - 客户邮箱属于公司
    + mifanId (Long) - 米饭星id,默认为0
    + priority  (int) - 优先级 (优先级，0-低，1-中，2-高)
    + companyId  (Long) - 公司id
    + accountSource  (int) - 账号来源，(0-注册用户，1-展会用户，2-网络邮箱，3-合作伙伴)
    + retry  (int) - 重试次数
    + sendCount  (int) - 是否发送 （0-未发，1-已发）
    + disableReason (String) --禁用原因
    + enabled (int) - 是否可用（0为禁用 1为可用）
    + creator (Long)  - 创建人
    + modifier (Long) - 修改人
    + created (Date) - 创建时间
    + modified (Date) - 修改时间 
    + visitLink (Long) - 链接访问数

### 增加 [POST] /email
+ Description
  + [MUST] authenticated
  + [MUST] ROLE_ADMIN

+ Parameters
    + email (String) - email账户 必填
    + lastName (String) - 姓氏
    + name (String)     - 名字
    + positionalTitles (String) - 职称
    + emailCompany (String) - 客户邮箱属于公司
    + priority  (int) - 优先级
    + companyId  (Long) - 公司id
    + accountSource  (int) - 账号来源，(0-注册用户，1-展会用户，2-网络邮箱，3-合作伙伴)

+ Request (application/json)

       {
	    "data":{
		"email":"1112525524@qq.com",
		"companyId":"1",
		"accountSource":"1",
		"lastName":"刘",
		"name":"凯",
		"positionalTitles":"职称",
		"emailCompany":"宝迪"
	}
}
+ Response 200 


### 修改 [PATCH] /email/{id} 

+ Description
  + [MUST] authenticated
  + [MUST] ROLE_ADMIN

+ Parameters
    + companyName 必填  
    + companyDesc 

+ Request (application/json)
+ 
        {
	    "data":{
		"email":"1112525524@qq.com",
		"companyId":"1",
		"accountSource":"1",
		"lastName":"刘",
		"name":"凯1",
		"positionalTitles":"职称1",
		"emailCompany":"宝迪"
	}
}

+ Response 200  (application/json)


### 查询email详情 [GET] /email/{id}
+ Parameters
    + id 
    
+ Request (application/json)
       
        {
        "data": {
        "id": 1,
        "enabled": 1,
        "creator": 0,
        "modifier": 0,
        "created": "2018-11-12 18:05:07",
        "modified": "2018-12-05 14:03:37",
        "email": "yangchangli0010@gmail.com",
        "sendCount": 1,
        "retry": 0,
        "lastName": "杨",
        "name": "昌立",
        "positionalTitles": "工程师",
        "emailCompany": "A公司",
        "mifanId": 0,
        "priority": 1,
        "companyId": 1,
        "accountSource": 0,
        "companyName": "mm"
    }
}

+ Response 200

### 查询邮件账户列表 [GET]  /email
+ Description
  + [MUST] authenticated
  + [MUST] ROLE_ADMIN

+ Parameters
    + page[number] (int)  页码
    + page[size]  (int)   页尺
    + filter[emailId] (Long)   Email ID
    + filter[emailAddr] (String) Email Address
    + filter[companyId] (Long)  公司ID
    + filter[priority] (Integer)  优先级(0-低，1-中，2-高)
    + filter[enabled] (Integer)  是否可用(1-启用，0-禁用)
    
+ Response 200 (application/json)

        {
        "meta": {
        "totalPages": 42,
        "totalElements": 413,
        "size": 10,
        "number": 1,
        "numberOfElements": 10,
        "first": true,
        "last": false,
        "sort": null
        },
        "links": {
        "self": "/email?filter[enabled]=1&page[number]=1&page[size]=10",
        "first": "/email?filter[enabled]=1&page[number]=1&page[size]=10",
        "next": "/email?filter[enabled]=1&page[number]=2&page[size]=10",
        "last": "/email?filter[enabled]=1&page[number]=42&page[size]=10"
        },
        "data": [
        {
            "id": 1,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-11-12 18:05:07",
            "modified": "2018-12-05 14:03:37",
            "email": "yangchangli0010@gmail.com",
            "sendCount": 1,
            "retry": 0,
            "lastName": "杨",
            "name": "昌立",
            "positionalTitles": "工程师",
            "emailCompany": "A公司",
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm",
            "visitLink": 0
        },
        {
            "id": 2,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-10-23 14:23:32",
            "modified": "2018-12-05 14:03:36",
            "email": "yangchangli@mifanxing.com",
            "sendCount": 1,
            "retry": 0,
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm",
            "visitLink": 0
        },
        {
            "id": 3,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-11-13 11:41:07",
            "modified": "2018-11-28 15:58:46",
            "email": "ycl0010@sina.com",
            "sendCount": 0,
            "retry": 0,
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm",
            "visitLink": 0
        },
        {
            "id": 4,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-10-18 16:18:43",
            "modified": "2018-12-05 14:03:36",
            "email": "1223944885@qq.com",
            "sendCount": 1,
            "retry": 0,
            "disableReason": "",
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm",
            "visitLink": 18
        },
        {
            "id": 5,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-10-22 14:17:00",
            "modified": "2018-12-05 14:03:36",
            "email": "17085145710@163.com",
            "sendCount": 1,
            "retry": 0,
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm",
            "visitLink": 0
        },
        {
            "id": 6,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-10-22 14:31:00",
            "modified": "2018-12-05 14:03:41",
            "email": "yangchangli1223944885@hotmail.com",
            "sendCount": 1,
            "retry": 0,
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm",
            "visitLink": 0
        },
        {
            "id": 9,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-10-23 13:56:18",
            "modified": "2018-12-05 14:03:47",
            "email": "zhangyongwei@mifanxing.com",
            "sendCount": 1,
            "retry": 0,
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm",
            "visitLink": 6
        },
        {
            "id": 10,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-10-23 13:56:59",
            "modified": "2018-12-05 14:03:52",
            "email": "cuiyan@mifanxing.com",
            "sendCount": 1,
            "retry": 0,
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm",
            "visitLink": 0
        },
        {
            "id": 12,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-10-23 13:58:42",
            "modified": "2018-12-05 14:03:57",
            "email": "guoliangwei@mifanxing.com",
            "sendCount": 1,
            "retry": 0,
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm",
            "visitLink": 7
        },
        {
            "id": 13,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-10-23 14:00:10",
            "modified": "2018-12-05 14:04:03",
            "email": "zhangxinya@mifanxing.com",
            "sendCount": 1,
            "retry": 0,
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm",
            "visitLink": 0
        }
    ]
} 



### 删除 [DELETE] /email/{id}
+ Description
  + [MUST]  Authenticated
  + [MUST] ROLE_ADMIN 
+  Response 200





+ 2018年12月10日
     + API初始化
     
## 邮件管理 -公司
+ Data
    + id (Long) - ID
    + companyName (String) - 公司名字
    + companyDesc (String) - 公司描述
    + enabled (int) - 是否可用 0为禁用 1为可用
    + created (Date) - 创建时间
    + modified (Date) - 修改时间    

### 增加 [POST] /company
+ Description
  + [MUST] authenticated
  + [MUST] ROLE_ADMIN

+ Parameters
    + companyName 必填  
    + companyDesc 

+ Request (application/json)

    {
	    "data":{
		    "companyName":"MIDIFAN",
		    "companyDesc":"一个关于音频设备的网站"
	    }
    }
+ Response 200 

### 修改 [PATCH] /company/{id} 

+ Description
  + [MUST] authenticated
  + [MUST] ROLE_ADMIN

+ Parameters
    + companyName 必填  
    + companyDesc 

+ Request (application/json)
+ 

         {
        "data" : {
              "id":8,
    		  "companyName" : "MIDIFAN11",
    		  "companyDesc" : "一个关于音频设备的网站"
    	  }
    }

+ Response 200 


### 查询公司详情 [GET] /company/{id}
+ Parameters
    + id 
    
+ Request (application/json)
       
         {
        "data": {
        "id": 11,
        "enabled": 1,
        "created": "2018-12-11 14:59:07",
        "modified": "2018-12-11 15:23:27",
        "companyName": "mm",
        "companyDesc": "一个关于音频设备的网站",
    }
}

+ Response 200

### 查询公司列表 [GET]  /company
+ Description
  + [MUST] authenticated
  + [MUST] ROLE_ADMIN

+ Parameters
    + page[number] (int)  页码
    + page[size]  (int)   页尺
    + filter[id] (Long)   公司ID
    + filter[companyName] (String) 公司名字
    
+ Response 200 (application/json)

        {
        "meta": {
        "totalPages": 1,
        "totalElements": 9,
        "size": 10,
        "number": 1,
        "numberOfElements": 9,
        "first": true,
        "last": true,
        "sort": null
        },
        "links": {
        "self": "/company?page[number]=1&page[size]=10",
        "first": "/company?page[number]=1&page[size]=10",
        "last": "/company?page[number]=1&page[size]=10"
        },
        "data": [
        {
            "id": 2,
            "enabled": 1,
            "created": "2018-11-27 10:40:56",
            "modified": "2018-11-27 10:40:59",
            "companyName": "太平宝迪"
        },
        {
            "id": 11,
            "enabled": 1,
            "created": "2018-12-11 14:59:07",
            "modified": "2018-12-11 15:23:27",
            "companyName": "mm",
            "companyDesc": "一个关于音频设备的网站"
        },
        {
            "id": 14,
            "enabled": 1,
            "created": "2018-12-11 14:59:27",
            "modified": "2018-12-11 14:59:27",
            "companyName": "MI33DIFAN33111",
            "companyDesc": "一个关于音频设备的网站"
        },
        {
            "id": 17,
            "enabled": 1,
            "created": "2018-12-11 15:03:02",
            "modified": "2018-12-11 15:03:02",
            "companyName": "dfdfdf",
            "companyDesc": "一个关于音频设备的网站"
        },
        {
            "id": 18,
            "enabled": 1,
            "created": "2018-12-11 15:04:52",
            "modified": "2018-12-11 15:04:52",
            "companyName": "1dfdfdf",
            "companyDesc": "一个关于音频设备的网站"
        },
        {
            "id": 19,
            "enabled": 1,
            "created": "2018-12-11 15:07:40",
            "modified": "2018-12-11 15:07:40",
            "companyName": "1d23fdfdf",
            "companyDesc": "一个关于音频设备的网站"
        },
        {
            "id": 20,
            "enabled": 1,
            "created": "2018-12-11 15:11:19",
            "modified": "2018-12-11 15:11:19",
            "companyName": "133d23fdfdf",
            "companyDesc": "一个关于音频设备的网站"
        },
        {
            "id": 23,
            "enabled": 1,
            "created": "2018-12-11 15:16:33",
            "modified": "2018-12-11 15:16:33",
            "companyName": "333133d2333223fdfdf",
            "companyDesc": "一个关于音频设备的网站"
        },
        {
            "id": 25,
            "enabled": 1,
            "created": "2018-12-11 15:20:04",
            "modified": "2018-12-11 15:20:04",
            "companyName": "A333133d23222233223fdfdf",
            "companyDesc": "一个关于音频设备的网站"
        }
    ]
}



### 删除 [DELETE] /company/{id}
+ Description
  + [MUST]  Authenticated
  + [MUST] ROLE_ADMIN 
+  Response 200



## 邮件管理 -NewsLetter
+ Data
    + id (Long) - ID
    + subject (String) - 邮件主题
    + newsletterLink (String) - 邮件内容链接
    + created (Date) - 创建时间
    + modified (Date) - 修改时间    

### 增加 [POST] /newsletter
### 修改 [PATCH] /newsletter/{id} 
### 查询newsletter详情 [GET] /newsletter/{id}
### 查询newsletter列表 [GET]  /newsletter
+ Description
  + [MUST] authenticated
  + [MUST] ROLE_ADMIN

+ Parameters
    + page[number] (int)  页码
    + page[size]  (int)   页尺
+ Response 200 (application/json)

        {
        "meta": {
        "totalPages": 1,
        "totalElements": 3,
        "size": 10,
        "number": 1,
        "numberOfElements": 3,
        "first": true,
        "last": true,
        "sort": null
        },
        "links": {
        "self": "/newsletter?page[number]=1&page[size]=10",
        "first": "/newsletter?page[number]=1&page[size]=10",
        "last": "/newsletter?page[number]=1&page[size]=10"
        },
        "data": [
        {
            "id": 1,
            "created": "2018-11-12 16:42:00",
            "modified": "2018-11-12 16:42:00",
            "newsletterLink": "http://www.mifanxing.com/api/wxrank/newsletter/index/1?templateNo=1",
            "subject": "音视频行业每周精要"
        },
            {
            "id": 2,
            "created": "2018-12-05 13:29:27",
            "modified": "2018-12-05 13:29:31",
            "newsletterLink": "http://www.mifanxing.com/api/wxrank/newsletter/index/2?templateNo=1",
            "subject": "音视频行业每周精要"
        },
            {
            "id": 3,
            "created": "2018-12-11 09:46:46",
            "modified": "2018-12-11 09:46:48",
            "newsletterLink": "http://www.mifanxing.com/api/wxrank/newsletter/index/3?templateNo=1",
            "subject": "音视频行业每周精要"
        }
    ]
}

### 删除 [DELETE] /newsletter/{id}
+ Description
  + [MUST]  Authenticated
  + [MUST] ROLE_ADMIN 
+  Response 200


+ 2018年12月13日
     + API初始化
     
## 邮件管理-日志查看
+ Data
    + id (Long) - ID 链接ID
    + link (String) - 链接地址
    + newsletterId (Long) - 所属期号
    + module (String) --所属模块
    + visitTimes  (Long) - 访问次数

### 查询日志查看列表 [GET]  /log
+ Description
  + [MUST] authenticated
  + [MUST] ROLE_ADMIN

+ Parameters
    + filter[link] (String) - 查询链接
    + filter[module] (String) -模块(product 热门产品， weekly 热门周刊，list 大数据榜单)
    + filter[visitTimes] (String) -排序(asc 从小到大  desc 从大到小)
    
+ Response 200 (application/json)

        {
        "meta": {
        "totalPages": 5,
        "totalElements": 43,
        "size": 10,
        "number": 1,
        "numberOfElements": 10,
        "first": true,
        "last": false,
        "sort": null
        },
        "links": {
        "self": "/log?page[number]=1&page[size]=10",
        "first": "/log?page[number]=1&page[size]=10",
        "next": "/log?page[number]=2&page[size]=10",
        "last": "/log?page[number]=5&page[size]=10"
        },
        "data": [
        {
            "id": 82,
            "newsletterId": 1,
            "link": "http://mifanxing.cn:7778/email/unsubscribe?emailId=227",
            "module": "product",
            "visitTimes": 1
        },
        {
            "id": 210,
            "newsletterId": 1,
            "link": "http://mifanxing.cn:7778/email/unsubscribe?emailId=2339",
            "module": "product",
            "visitTimes": 1
        },
        {
            "id": 173,
            "newsletterId": 1,
            "link": "http://mifanxing.cn:7778/email/unsubscribe?emailId=4840",
            "module": "product",
            "visitTimes": 1
        },
        {
            "id": 169,
            "newsletterId": 1,
            "link": "http://mifanxing.cn:7778/email/unsubscribe?emailId=5013",
            "module": "product",
            "visitTimes": 2
        },
        {
            "id": 85,
            "newsletterId": 1,
            "link": "http://www.mifanxing.com/channel/86",
            "visitTimes": 1
        },
        {
            "id": 14,
            "newsletterId": 1,
            "link": "http://www.mifanxing.com/products",
            "module": "product",
            "visitTimes": 6
        },
        {
            "id": 298,
            "newsletterId": 1,
            "link": "https://www.mifanxing.com/cooperation/ev50/",
            "visitTimes": 5
        },
        {
            "id": 105,
            "newsletterId": 1,
            "link": "https://www.mifanxing.com/p/1317870",
            "visitTimes": 6
        },
        {
            "id": 299,
            "newsletterId": 1,
            "link": "https://www.mifanxing.com/p/1474321",
            "visitTimes": 2
        },
        {
            "id": 50,
            "newsletterId": 1,
            "link": "https://www.mifanxing.com/p/1504241",
            "visitTimes": 4
        }
    ]
}




### 查询汇总(打开率,回复率，送达率) [GET]  /log/summarize/{newsLetterId}
+ Data
    + sendAmount (Long)  实际发送数量
    + deliveryFailAmount (Long)  发送失败数量
    + sendSuccessAmount (Long)  发送成功数量
    + deliverability (double) 送达率
    + openCount (Long)  打开数量
    + noOpenCount (Long)  未打开数量
    + openRate (double) 打开率
    + reversionCount (Long) 回复数量
    + noReversionCount (Long) 没有回复数量
    + reversionRate  (Double) 回复率
    + id (Long) - ID 链接ID
    + link (String) - 链接地址
    + module (String) --所属模块（weekly 热门周刊，product 热门产品，list 大数据榜单）
    + visitTimes  (Long) - 访问次数

+ Description
  + [MUST] authenticated
  + [MUST] ROLE_ADMIN

+ Parameters
    + newsLetterId (int) Newsletter ID   
    
+ Response 200 (application/json)

        {
        "meta": {
        "totalPages": 1,
        "totalElements": 3,
        "size": 10,
        "number": 1,
        "numberOfElements": 3,
        "first": true,
        "last": true,
        "sort": null,
        "sendAmount": 5219,
        "deliveryFailAmount": 1,
        "sendSuccessAmount": 5218,
        "deliverability": "99.98%",
        "openCount": 86,
        "noOpenCount": 5133,
        "openRate": "1.65%",
        "reversionCount": 1,
        "noReversionCount": 5218,
        "reversionRate": "0.02%"
        },
        "links": {
        "self": "/log/summarize/3?page[number]=1&page[size]=10",
        "first": "/log/summarize/3?page[number]=1&page[size]=10",
        "last": "/log/summarize/3?page[number]=1&page[size]=10"
        },
        "data": [
        {
            "id": 1,
            "created": "2018-12-17 11:37:59",
            "period": 3,
            "link": "https://www.mifanxing.com/p/1538018?module=weekly",
            "module": "weekly",
            "visitTimes": 14
        },
        {
            "id": 2,
            "created": "2018-12-17 11:38:19",
            "period": 3,
            "link": "https://www.mifanxing.com/p/1535346?module=list",
            "module": "list",
            "visitTimes": 4
        },
        {
            "id": 3,
            "created": "2018-12-17 11:40:29",
            "period": 3,
            "link": "https://www.mifanxing.com/cooperation/ev50/?module=product",
            "module": "product",
            "visitTimes": 2
        }
        ]
        }




### 查询打开率 [GET]  /log/openrate/{newsLetterId}
+ Data
    + sendAmount (Long)  实际发送数量
    + openCount (Long)  打开数量
    + noOpenCount (Long)  未打开数量
    + openRate (double) 打开率
    + emailId (Long) - 邮箱ID
    + emailAddress (String) - email地址
    + created (String) -打开时间
    

+ Description
  + [MUST] authenticated
  + [MUST] ROLE_ADMIN

+ Parameters
    + newsLetterId (int) Newsletter ID   
    
+ Response 200 (application/json)

        {
        "meta": {
        "totalPages": 15,
        "totalElements": 144,
        "size": 10,
        "number": 1,
        "numberOfElements": 10,
        "first": true,
        "last": false,
        "sort": null,
        "sendAmount": 5219,
        "openAmount": 86,
        "noOpenCount": 5133,
        "openRate": "1.65%"
        },
        "links": {
        "self": "/log/openrate/3?page[number]=1&page[size]=10",
        "first": "/log/openrate/3?page[number]=1&page[size]=10",
        "next": "/log/openrate/3?page[number]=2&page[size]=10",
        "last": "/log/openrate/3?page[number]=15&page[size]=10"
        },
        "data": [
        {
            "id": 707,
            "created": "2018-12-12 16:53:41",
            "emailId": 4,
            "newsletterId": 3,
            "tableDiff": 1,
            "emailAddress": "1223944885@qq.com"
        },
        {
            "id": 712,
            "created": "2018-12-12 16:58:35",
            "emailId": 84,
            "newsletterId": 3,
            "tableDiff": 1,
            "emailAddress": "850770722@qq.com"
        },
        {
            "id": 715,
            "created": "2018-12-12 16:58:46",
            "emailId": 19,
            "newsletterId": 3,
            "tableDiff": 1,
            "emailAddress": "zhangtengli@mifanxing.com"
        },
        {
            "id": 715,
            "created": "2018-12-12 16:58:46",
            "emailId": 19,
            "newsletterId": 3,
            "tableDiff": 1,
            "emailAddress": "zhangtengli@mifanxing.com"
        },
        {
            "id": 718,
            "created": "2018-12-12 17:00:10",
            "emailId": 84,
            "newsletterId": 3,
            "tableDiff": 1,
            "emailAddress": "850770722@qq.com"
        },
        {
            "id": 718,
            "created": "2018-12-12 17:00:10",
            "emailId": 84,
            "newsletterId": 3,
            "tableDiff": 1,
            "emailAddress": "850770722@qq.com"
        },
        {
            "id": 720,
            "created": "2018-12-12 17:00:31",
            "emailId": 84,
            "newsletterId": 3,
            "tableDiff": 1,
            "emailAddress": "850770722@qq.com"
        },
        {
            "id": 720,
            "created": "2018-12-12 17:00:31",
            "emailId": 84,
            "newsletterId": 3,
            "tableDiff": 1,
            "emailAddress": "850770722@qq.com"
        },
        {
            "id": 727,
            "created": "2018-12-12 17:02:32",
            "emailId": 471,
            "newsletterId": 3,
            "tableDiff": 1,
            "emailAddress": "kai.liu@budee.cn"
        },
        {
            "id": 727,
            "created": "2018-12-12 17:02:32",
            "emailId": 471,
            "newsletterId": 3,
            "tableDiff": 1,
            "emailAddress": "kai.liu@budee.cn"
        }
        ]
        }

### 查询送达率 [GET]  /log/deliverability/{newsLetterId}/1  (送达成功)
+ Data
    + sendAmount (Long)  实际发送数量
    + deliverySuccessAmount (Long)  送达成功数量
    + deliveryFailAmount (Long)  送达失败数量
    + deliverability (Double) 送达率
    + emailId (Long) - 邮箱ID
    + emailAddress (String) - email地址
    + created (String) -送达时间
    

+ Description
  + [MUST] authenticated
  + [MUST] ROLE_ADMIN

+ Parameters
    + newsLetterId (int) Newsletter ID   
    
+ Response 200 (application/json)

        {
        "meta": {
        "totalPages": 522,
        "totalElements": 5218,
        "size": 10,
        "number": 1,
        "numberOfElements": 10,
        "first": true,
        "last": false,
        "sort": null,
        "sendAmount": 5219,
        "deliveryFailAmount": 1,
        "deliverySuccessAmount": 5218,
        "deliverability": "99.98%"
        },
        "links": {
        "self": "/log/deliverability/3/1?page[number]=1&page[size]=10",
        "first": "/log/deliverability/3/1?page[number]=1&page[size]=10",
        "next": "/log/deliverability/3/1?page[number]=2&page[size]=10",
        "last": "/log/deliverability/3/1?page[number]=522&page[size]=10"
        },
        "data": [
        {
            "id": 1,
            "created": "2018-12-12 16:53:26",
            "newsletterId": 3,
            "emailId": 166,
            "companyId": 1,
            "tableDiff": 1,
            "emailAddress": "romaholidays@foxmail.com"
        },
        {
            "id": 1,
            "created": "2018-12-12 16:53:26",
            "newsletterId": 3,
            "emailId": 166,
            "companyId": 1,
            "tableDiff": 1,
            "emailAddress": "romaholidays@foxmail.com"
        },
        {
            "id": 2,
            "created": "2018-12-12 16:53:26",
            "newsletterId": 3,
            "emailId": 5,
            "companyId": 1,
            "tableDiff": 1,
            "emailAddress": "17085145710@163.com"
        },
        {
            "id": 2,
            "created": "2018-12-12 16:53:26",
            "newsletterId": 3,
            "emailId": 5,
            "companyId": 1,
            "tableDiff": 1,
            "emailAddress": "17085145710@163.com"
        },
        {
            "id": 3,
            "created": "2018-12-12 16:53:27",
            "newsletterId": 3,
            "emailId": 79,
            "companyId": 1,
            "tableDiff": 1,
            "emailAddress": "fuzhian@126.com"
        },
        {
            "id": 3,
            "created": "2018-12-12 16:53:27",
            "newsletterId": 3,
            "emailId": 79,
            "companyId": 1,
            "tableDiff": 1,
            "emailAddress": "fuzhian@126.com"
        },
        {
            "id": 4,
            "created": "2018-12-12 16:53:27",
            "newsletterId": 3,
            "emailId": 2,
            "companyId": 1,
            "tableDiff": 1,
            "emailAddress": "yangchangli@mifanxing.com"
        },
        {
            "id": 4,
            "created": "2018-12-12 16:53:27",
            "newsletterId": 3,
            "emailId": 2,
            "companyId": 1,
            "tableDiff": 1,
            "emailAddress": "yangchangli@mifanxing.com"
        },
        {
            "id": 10,
            "created": "2018-12-12 16:53:37",
            "newsletterId": 3,
            "emailId": 21,
            "companyId": 1,
            "tableDiff": 1,
            "emailAddress": "050100cui@163.com"
        }
        ]
        }

### 查询送达率失败 [GET]  /log/deliverability/{newsLetterId}/0  (送达失败)
+ Data
    + sendAmount (Long)  实际发送数量
    + deliverySuccessAmount (Long)  送达成功数量
    + deliveryFailAmount (Long)  送达失败数量
    + deliverability (Double) 送达率
    + emailId (Long) - 邮箱ID
    + emailAddress (String) - email地址
    + content (String) -失败原因
    

+ Description
  + [MUST] authenticated
  + [MUST] ROLE_ADMIN

+ Parameters
    + newsLetterId (int) Newsletter ID   
    
+ Response 200 (application/json)

        {
        "meta": {
        "totalPages": 1,
        "totalElements": 1,
        "size": 10,
        "number": 1,
        "numberOfElements": 1,
        "first": true,
        "last": true,
        "sort": null,
        "sendAmount": 5219,
        "deliveryFailAmount": 1,
        "deliverySuccessAmount": 5218,
        "deliverability": "99.98%"
        },
        "links": {
        "self": "/log/deliverability/3/0?page[number]=1&page[size]=10",
        "first": "/log/deliverability/3/0?page[number]=1&page[size]=10",
        "last": "/log/deliverability/3/0?page[number]=1&page[size]=10"
        },
        "data": [
        {
            "id": 2,
            "created": "2018-12-17 11:35:17",
            "type": 0,
            "tableDiff": 2,
            "emailId": 0,
            "newsletterId": 3,
            "edmLogId": 2334,
            "content": "1",
            "backReversion": 1545017699000
        }
        ]
        }
        
### 查询回复率 [GET]  /log/reversionrate/{newsLetterId}
+ Data
    + sendAmount (Long)  实际发送数量
    + reversionCount (Long)  回复数量
    + noReversionCount (Long)  没有回复数量
    + reversionRate (Double) 回复率率
    + id (Long) - ID
    + emailAddress (String) - email地址
    + content (String) -回复内容
    + created (String) -回复时间
  
    
+ Description
  + [MUST] authenticated
  + [MUST] ROLE_ADMIN

+ Parameters
    + newsLetterId (int) Newsletter ID   
    
+ Response 200 (application/json)

        {
        "meta": {
        "totalPages": 1,
        "totalElements": 1,
        "size": 10,
        "number": 1,
        "numberOfElements": 1,
        "first": true,
        "last": true,
        "sort": null,
        "sendAmount": 5219,
        "reversionCount": 1,
        "noReversionCount": 5218,
        "reversionRate": "0.02%"
        },
        "links": {
        "self": "/log/reversionrate/3?page[number]=1&page[size]=10",
        "first": "/log/reversionrate/3?page[number]=1&page[size]=10",
        "last": "/log/reversionrate/3?page[number]=1&page[size]=10"
        },
        "data": [
        {
            "id": 1,
            "created": "2018-12-17 11:34:28",
            "type": 1,
            "tableDiff": 1,
            "emailId": 1,
            "newsletterId": 3,
            "edmLogId": 233,
            "content": "22",
            "backReversion": 1545017663000,
            "emailAddress": "yangchangli0010@gmail.com"
        }
        ]
        }




