---
layout:     post
title:      Mocha Scope 之间执行顺序
date:       2017-03-12 20:16:00
author:     JoneWeng
summary:    mocha order of execute
categories: jekyll
thumbnail:  jekyll
minutes : 2
tags:
 - Mocha
 - nodejs
 - test
---

### 测试代码
{% highlight ruby %}
describe('outer', function() {
    before(function() {
        print(`outer before`, )
    });

    after(function() {
        print(`outer after`, )
    });

    beforeEach(function() {
        print(`outer beforeEach`, )
    });

    afterEach(function() {
        print(`outer afterEach`, )
    })

    describe('inner', () => {
        before(function() {
            print(`inner before`, )
        })

        after(function() {
            print(`inner after`, )
        })

        beforeEach(function() {
            print(`inner beforeEach`, )
        })

        afterEach(function() {
            print(`inner afterEach`, )
        })

        it('it case', () => {
            print(`inner it case`, )
        })
    })
})

{% endhighlight %}

## 输出
![result](https://ww4.sinaimg.cn/large/006tKfTcly1fdlis7tmxij30ha0bi75e.jpg)
