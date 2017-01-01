# -*- coding=utf-8 -*-

import urllib.request                   #调用必要模块
import re                               #调用正则表达式模块


url1 = 'http://55po.com/kawd-515.html/' #第一部分网址
url2 = ''                               #第二部分网址
num = list(range(1,8))                  #网址变量部分
for x in num:
        fullurl = (url1)+str(x)+(url2)  #网址命名规则
        print ("准备获取",fullurl)
        req = urllib.request.urlopen(fullurl)
        buf = req.read()
        buf = buf.decode('utf-8')
        
        giflisturl = re.findall(r'src=.+\.gif',buf)  #查找buf中的src=开头，.gif结尾的链接
        giflisturl = re.findall(r'http:.+\.gif',buf) #查找buf中的http:开头，.gif结尾的链接
        jpglisturl = re.findall(r'src=.+\.jpg',buf)  #查找buf中的src=开头，.jpg结尾的链接
        jpglisturl = re.findall(r'http:.+\.jpg',buf) #查找buf中的http:开头，.jpg结尾的链接

        i=0
        for gif in giflisturl:  
            f=open(r"c:\1"+'/'+str(x*100)+str(i)+'.gif','wb')  #保存查找到的文件，定义保存路径及命名规则
            req=urllib.request.urlopen(gif)  
            buf=req.read()  
            f.write(buf)  
            i+=1
            print ("下载gif完成"+str(x*100)+str(i))
        
       
        for jpg in giflisturl:  
            f=open(r"c:\1"+'/'+str(x*100)+str(i)+'.jpg','wb')  #保存查找到的文件，定义保存路径及命名规则
            req=urllib.request.urlopen(jpg)  
            buf=req.read()  
            f.write(buf)  
            i+=1
            print ("下载jpg完成"+str(x*100)+str(i))
        print ("下载完成",fullurl)
