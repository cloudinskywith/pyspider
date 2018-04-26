# pyspider
some api that i use in pyspider project


## 1.使用post请求
```py
self.crawl('http://academic.xxxx.edu.cn/Login', callback=self.callback,
               method='POST', data={'xxx': '*********', 'xxx': '****'})
```
>"POST"必须为大写

## 2.如何动态爬取下一页（html模式）
```py
def index_page(self, response):
        for each in response.doc('.content-data-report .download-book a').items():
            print(each)
            self.crawl(each.attr.href, callback=self.detail_page)

        # 继续下一页,有next说明有下一页 (".results-page .active")
        next_page = response.doc('.next')
        current =(response.doc(".results-page .active"))
        if next_page:
            next = int(current) + 1
            self.crawl(f'xxxx&page={next}',callback=self.detail_page)
        else:
            print("没有下一页")
```

## 3.如何动态爬取下一页（接口模式）
这个就简单很多了
