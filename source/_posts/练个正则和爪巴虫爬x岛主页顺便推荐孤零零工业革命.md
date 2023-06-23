---
title: 练个正则和爪巴虫，爬x岛主页，顺便推荐孤零零工业革命
date: 2023-06-23 17:03:30
tags: python
---

# 考完试不想卷

我时常在想，爱好是什么呢，现在或许有答案了，就是折腾一些看似有用实则纯粹浪费时间的东西，跟打游戏也没两样。

```python
import requests
import re
url = 'https://www.nmbxd1.com/Forum/timeline/id/1'
response = requests.get(url)
response.encoding = 'utf-8'

titles=re.findall(r'<div class="h-threads-content">([\S\s]*?)</div>',response.text)
with open ('test.txt','w',encoding='utf-8') as f:
    for title in titles:
        title=title.strip()
        title=re.sub(r'<.*?>','',title)
        title=re.sub(r'&gt;&gt;No\w*?','',title)
        title=re.sub(r'\.\w*?','',title)
        print(title)
        f.write(title+'\n')

```

### 知道这个博客的比知道我推特的人还少，所以就真当垃圾桶了写点垃圾话

我时常想，我学这些东西的意义是什么。我清楚的知道我在瞎搞，是脚本小子，是调包侠，没学到什么真东西。而且还穷，还抠，不愿意为自己付出。

我后来这么觉得，我学这些，学的只是个高兴。确实，写py让心里平静。

这里推一首曲子，写py的时候常听的，能让心里平静的。

<iframe src="//player.bilibili.com/player.html?aid=224286578&bvid=BV1D8411T7Z2&cid=1007464575&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

挺喜欢mc的，只是这两年浮躁了。
赶着去投胎呢。