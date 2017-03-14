---
layout:     post
title:      Mocha Scope 之间执行顺序
date:       2017-03-12 20:16:00
author:     JoneWeng
summary:    mocha order of execute
categories: Node.js
thumbnail:  coffee
minutes : 2
tags:
 - Mocha
 - Node.js
 - test
---

### _TL;DR_


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

### 输出
![result](https://ww4.sinaimg.cn/large/006tKfTcly1fdmpt2foywj30qu0c4wfp.jpg)
