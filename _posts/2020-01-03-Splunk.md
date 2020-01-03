---
layout: post
title:  "Splunk学习日记"
categories: Splunk
tags:  splunk  
author: momo
---

* content
{:toc}


## 前言

关于Splunk使用过程中的一些常用查询功能。

##  一、获取时间
1、获取当前时间
| eval timestamp=strftime(now(),"%Y-%m-%d %H:%M:%S")

2、30分钟前的时间归为当前小时，30分钟后的归到下一个小时
| eval timestamp=if(strftime(now(),"%M")>="30",strftime(relative_time(now(),"+1h@h"),"%Y-%m-%d %H")+":00:00",strftime(now(),"%Y-%m-%d %H")+":00:00")

## 二、







