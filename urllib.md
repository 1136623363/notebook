# 一个类型 http.client.HTTPResponse
#六个方法read readline readlines getcode getyrl getheaders
getcode() 返回状态码
getheaders() 返回响应头

# request下载
```
import urllib.request  
  
url = 'http://www.baidu.com'  
  
urllib.request.urlretrieve(url,'baidu.html')  
  
  
url_img = 'https://img1.baidu.com/it/u=272403300,1009147969&fm=253&fmt=auto&app=138&f=JPEG?w=509&h=500'  
urllib.request.urlretrieve(url_img,'test.img')  
  
url_video = 'https://www.youtube.com/d66cbac8-319e-4bac-8348-b3bc53e8c534'  
  
urllib.request.urlretrieve(url_video,'test.mp4')
```

# url组成和请求定制

```
import urllib.request  
  
url = 'https://www.baidu.com'  
  
#url组成  
#http\https  www.baidu.com   80\443      s     wd=      #  
#协议          主机             端口号     路径    参数     锚点  
  
  
  
header = {'User-Agent' : 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/105.0.0.0 Safari/537.36 Edg/105.0.1343.27'}  
#urlopen 不能存储字典 所以header不能直接传进去  
  
#注意 由于参数顺序问题 不能直接写url和header 因为中间还有个参数data  
request = urllib.request.Request(url=url,headers=header)  
response = urllib.request.urlopen(request)  
  
content = response.read().decode('utf-8')  
  
print(content)
```
![输入图片说明](/imgs/2022-11-16/SjmpEyvsORQ8hRDc.png)

# 编解码

ASCII编码
A:65 	a:122

Unicode把所有编码统一到一起



urllib.parse中quote
```
import urllib.request  
import urllib.parse  
  
url = 'https://www.baidu.com/s?wd='  
  
header = {'User-Agent' :  
              'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/105.0.0.0 Safari/537.36 Edg/105.0.1343.27'  
}  
  
name = urllib.parse.quote('周杰伦')  
print(url+name)  
  
request = urllib.request.Request(url=url+name,headers=header)  
  
response = urllib.request.urlopen(request)  
  
content = response.read().decode('utf-8')  
print(content)
```


Post请求
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjcwNzAyNjEyXX0=
-->