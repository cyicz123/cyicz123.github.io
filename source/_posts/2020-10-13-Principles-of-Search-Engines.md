---
title: Principles of Search Engines
tags:
  - 英语
  - 搜索引擎
categories:
  - 英语
date: 2020-10-13 21:48:24
---

## What's the traditional principles of search engines?
Search engine is a computer program that helps users search for content they need. The traditional search engine consists of three modules as shown in the following.

<!-- more -->

搜索引擎是一个帮助用户搜索他们需要内容的计算机程序。传统搜索引擎由如下图所示的三个模块组成

![three modules](http://image.cyicz123.top/img/20201012000200.png)

### Web spider

Information on the Internet is spread all over the world. If a search engine wants to answer users’ searches, it must first rely on web spiders to store web pages on its own local server. Web spiders continuously send requests to various websites and store the obtained web pages. 

So how does it know where to send the request? Search engines usually use links between web pages to solve this question. Web spiders start from a web page, extract links to other pages, and treat them as the next request. Then Repeat this process over and over again. There are many details to be considered here. For example, how to avoid circularly linked web pages, how to parse web documents (usually in html format, but there are also many other formats), how to extract links inside, and how to handle errors when the link cannot be opened.

互联网上的信息遍布世界各地，搜索引擎要想回答用户的搜索，首先要依靠网路爬虫把网页存在自己本地的服务器上。 网络爬虫不停的向各种网站发送请求，将所得到的网页存储起来。那么它怎么知道往哪发送请求呢?搜索引擎通常的做法是利用网页之间的链接.网络爬虫从一个网页出发,提取出指向其他页面的链接，把它们当成将下次要请求的对象.然后不停重复这个过程。这里有很多细节要被考虑。例如如何避免循环链接的网页,如何解析网页文档(通常是html格式，但也有很多其他格式）如何提取里边的链接;当链接无法打开时如何对错误进行处理等。

### Index algorithm

How to find information in complex data?

Every word that appears in a document owned by a search engine has an inverted list. It records how many documents the word appears in, which documents are, how many times each document section appears, and where it appears respectively. 

For example, the word Apple appears in documents 1, 7, 19, 34, 102. Among them, document 1 appears 3 times, respectively at positions 20, 105, and 700. In this way, when searching for Apple, Google does not need to traverse all the documents, only need to find the inverted list corresponding to each word to know where the word appears. Every web document has more than just text information. It may also include URLs, file names, references, etc. In order to improve search quality, search engines need to process different parts of the document separately to construct a reverse list. Each part of the word must be added to the inverted list of words belonging to this part.

如何在繁杂的数据中找到信息？

搜索引擎所拥有的文档中出现的每一个单词都拥有一个反转列表。它记录了这个单词在多少文档中出现，分别是哪些文档，每个文档分部出现多少次，分别出现在什么位置等信息。比如Apple这个词出现在文档1，7，19，34，102。其中文档1中出现了3次，分别在位置20，105，700。这样当搜索Apple时，Goolge就不用遍历所有的文档，只需要查找每个单词对应的反转列表就可以知道这个词在哪里出现了。每一个网络文档不仅只有文本信息。它还可能包括URL，文件名，引用等部分。为了提高搜索质量，搜索引擎需要对文档的不同部分分别处理，构造反转列表。每一部分的单词都要被加入到这个词属于此部分的反转列表里。

### Search algorithm

If the search engine has an index, it can quickly find what users need. As mentioned earlier, search engines find matching content based on users' information needs. Information needs come from user input. How to understand it has many questions. Simply put, each search sentence will be parsed into a tree structure: leaf nodes are keywords. Then search based on keywords.

如果搜索引擎有了索引，它就可以快速找到用户所需内容了。前文说过搜索引擎根据用户的信息需求查找匹配的内容。信息需求来自于用户输入。如何理解它有很大学问。简单的说，每个搜索语句会被解析成一个树形结构:叶子节点就是一个个关键词.然后依据关键词检索.

## PageRank

### Introduction

The PageRank algorithm calculates the PageRank value of each web page, and then ranks the importance of the web pages according to the value of this value.

The core idea of the PageRank algorithm is that if a webpage is linked to by many other webpages, it means that this webpage is more important, that is, the PageRank value will be relatively high. And if a webpage with a high PageRank value links to another webpage, it will be linked The PageRank value of the web page you arrive will increase accordingly

PageRank算法计算每一个网页的PageRank值，然后根据这个值的大小对网页的重要性进行排序。PageRank算法的核心思想是如果一个网页被很多其他网页链接到的话说明这个网页比较重要，也就是PageRank值会相对较高.而且如果一个PageRank值很高的网页链接到一个其他的网页，那么被链接到的网页的PageRank值会相应地因此而提高

### Principle

$$
PR(A)=1-d+d(PR(T_1)/C(T_1)+\cdots+PR(T_n)/C(T_n))
$$

> PR(A) is the PR value of page A
>
> PR(Ti) is the PR value of page Ti, where page Ti refers to a certain page among all pages of A
>
> C(Ti) is the out degree of page Ti, that is, the number of edges where Ti points to other pages
>
> d is the damping coefficient, and its meaning is the probability that the user will continue to browse backwards after reaching a certain page at any time,
>
> PR(A)是页面A的PR值
>
> PR(Ti)是页面Ti的PR值，在这里，页面Ti是指向A的所有页面中的某个页面
>
> C(Ti)是页面Ti的出度，也就是Ti指向其他页面的边的个数
>
> d 为阻尼系数，其意义是，在任意时刻，用户到达某页面后并继续向后浏览的概率，

### Advantage

PageRank is a static algorithm that has nothing to do with queries. The PageRank value of all web pages is obtained through offline calculation; it effectively reduces the amount of calculation during online queries and greatly reduces the query response time.

PageRank是一个与查询无关的静态算法，所有网页的PageRank值通过离线计算获得；有效减少在线查询时的计算量，极大降低了查询响应时间。

## Personal thoughts on using Baidu

For individuals, Baidu's ranking algorithm is also PageRank.

个人觉得百度的排序算法也是PageRank

 ## Example 1

I recommend my personal blog site([cyicz123.top](cyicz123.top)) here. Since I only built the website a month ago, and no other websites reference my website. So I can’t find my website by searching keywords on Baidu.

我在这里推荐一下我的个人博客网站.由于一个月前我才建好网站,并且没有其他网站引用我的网站.所以我在百度上搜索关键词根本无法找到自己的网站.

![百度搜索逍遥小站](http://image.cyicz123.top/img/20201012010858.png)

![精准搜索网站](http://image.cyicz123.top/img/20201012010930.png)

### Example 2

But Baidu is not all the PageRank algorithm adopted. After Baidu's Fengchao system was launched in 2009, Baidu's page ranking and advertising ranking were officially separated. The front end of the Baidu search homepage is a promotion advertisement recommended based on search keywords. This is also one point that many people do not like Baidu.

但是百度也不全是采用的PageRank算法.从2009年百度的凤巢系统上线之后，百度网页排名和广告排名正式分开。百度搜索首页最前端是根据搜索关键词推荐的推广广告.这也是很多人不喜欢百度的一点.

![百度付费推广](http://image.cyicz123.top/img/20201012011701.png)