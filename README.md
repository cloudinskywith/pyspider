# pyspider
some api that i use in pyspider project


## 1.使用post请求
```py
self.crawl('http://academic.xxxx.edu.cn/Login', callback=self.callback,
               method='POST', data={'xxx': '*********', 'xxx': '****'})
```
>"POST"必须为大写

