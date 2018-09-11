---
layout: single
title: Exchange PowerShell | XmlException - For security reasons DTD is prohibited in this XML document.
date: 2018-09-11 20:00
category: 
tags: [exchange, powershell, exception, isp]
excerpt: Strange error when trying to connect to Exchange via PowerShell
header: 
  teaser: /content/2018/markdown.png
og_image: /content/2018/markdown.png
---

I was working from home today and was trying to connect to Exchange Online via PowerShell. Every time I tried to connect I would get the following error:

`System.Xml.XmlException: For security reasons DTD is prohibited in this XML document. To enable DTD processing set the DtdProcessing property on XmlReaderSettings to Parse and pass the settings into XmlReader.Create method.`

It was working fine in a RD session in the office but not at home. After a quick Google I saw a few other posts with people mentioning that it could be do with your ISP. Some have a "feature" called **Advanced Network Error Search** that will present a custom search page if a domain name cannot be resolved. That may be useful for some people but it turns out that was the problem.

[![Advanced Network Error Search]({{ site.url }}/content/2018/09/2018-09-11 20_19_17-Advanced Network Error Search.png.png)]({{ site.url }}/content/2018/09/2018-09-11 20_19_17-Advanced Network Error Search.png.png)

My ISP is Virgin Media and all I had to do was go [here](https://my.virginmedia.com/advancederrorsearch/settings) and change my selection to No - I would not like to use the advanced network error search. After a quick reboot of my modem everything was working and connecting as it should!