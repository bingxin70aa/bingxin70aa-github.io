---
layout: post
title: 当 Tableau 与 Pandas 碰撞出火花
categories: infovis
description:  绘制图表的基础是拥有一份完美的元素及其数据，但是数据往往没有想象那么“ 听话 ”，因此我们就要借用到 Pandas 来进行数据处理。
keywords: 图表,地图,绘制，数据，pandas
permalink: /posts/:categories/:title.html
---

> 绘制图表的基础是拥有一份完美的元素及其数据，但是数据往往没有想象那么“ 听话 ”，因此我们就要借用到 Pandas 来进行数据处理。
  
  假如需要绘制一份“关于中国排名前七的蛋糕店在我国分布情况 ”的地图，要如何抓取数据并进行简单的清理呢？请看：

```
import requests   #用於API HTTP requests
import pandas as pd   #使用pandas模块

def amap_api_search_by_keyword_city_code(kw, cc, api_key):  #使用高德地图api的关键字
    parameters = {"key":api_key}
    parameters.update({"keywords":kw,
                     "city":cc,
                     "citylimit": True
                     })
    pois = []  # 建构最终结果列表pois
    pg_no = 1  # 建构pg_no，每次给不一样的可选参数page值
    
    while True:  # 不断迭代，直到 break跳出
        parameters.update ({"page":pg_no})  #建构可选参数page值 为 pg_no
        
        r = requests.get("http://restapi.amap.com/v3/place/text", params=parameters)
        data = r.json()
        
        pois.extend(data['pois'])  # 使用Python列表之extend方法，把返回数据中的结果data['pois']存入pois
        no_pois_this_reserch = len(pois)  # 计算 累积实质结果数
        no_pois = int(data["count"])   # 计算 应有的实质数量
                      
        if (no_pois_this_reserch >= no_pois):   # 若 累积实质结果数 >= 应有的实质数量
            break  # 则结束迭代跳出
        else:
            pg_no += 1  # 否则找下一页数据，把 pg_no增1

    df_input = pd.DataFrame(pois)

    select_fields = "location	address	adname	cityname	id	importance	name	pname	tel	type	typecode".split("\t")  #将各元素进行分类切割
    df = df_input[select_fields]

    df = df.assign( 经 = [x.split(',')[0] for x in df['location']])
    df = df.assign( 纬 = [x.split(',')[1] for x in df['location']])  #分开经纬度
    return(df)
   
```
然后嵌入关键字及高德地图 api 的 key,记得换成自己申请的 key 哦。
```
df_yuanzushipin = amap_api_search_by_keyword_city_code(kw='元祖食品',cc='中国' , api_key='此处换成你的api_key')
df_haolilai = amap_api_search_by_keyword_city_code(kw='好利来', cc='中国' ,  api_key='此处换成你的api_key')
df_hagendasi= amap_api_search_by_keyword_city_code(kw='哈根达斯',cc='中国' ,  api_key='此处换成你的api_key')
df_miqi= amap_api_search_by_keyword_city_code(kw='米旗', cc='中国' ,  api_key='此处换成你的api_key')
df_nuoxin= amap_api_search_by_keyword_city_code(kw='诺心', cc='中国' ,  api_key='此处换成你的api_key')
df_balibeitian = amap_api_search_by_keyword_city_code(kw='巴黎贝甜', cc='中国' ,  api_key='此处换成你的api_key')
df_85duc= amap_api_search_by_keyword_city_code(kw='85duc', cc='中国' ,  api_key='此处换成你的api_key')
```
  
  
在图表末尾添加多一个类别 **keyword** ,并检查下有没有问题有

```
df_yuanzushipin['keywords']='元祖食品'
df_yuanzushipin
df_haolilai['keywords']='好利来'
df_haolilai
df_hagendasi['keywords']='哈根达斯'
df_hagendasi
df_miqi['keywords']='米旗'
df_miqi
df_nuoxin['keywords']='诺心'
df_nuoxin
df_balibeitian['keywords']='巴黎贝甜'
df_balibeitian
df_85duc['keywords']='85°C'
df_85duc
```  

将数据合并与重塑  

```
df= pd.concat([df_yuanzushipin , df_haolilai,df_hagendasi,df_miqi,df_nuoxin,df_balibeitian,df_85duc])
```
  
将数据输出tsv档命名为：amap_allcake

```
df.to_csv("amap_allcake.tsv", encoding="utf8", sep='\t') 
```


 - 此处感谢汉腾老师的教导，学艺不精，如若有更简便的方法或者是有问题的地方欢迎联系我。
