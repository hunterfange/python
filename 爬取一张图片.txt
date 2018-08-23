import requests
import os
#图片地址
url='https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1534770394147&di=8781e63bc5b6c7d57dc9c4cbf6187cf2&imgtype=0&src=http%3A%2F%2Fi9.qhimg.com%2Ft013a4f738dfa68899f.jpg'
root="F://python项目//爬虫//"#要保存到的文件目录
path=root+"樱花庄的宠物女孩.jpg"#文件目录+需要保存的名字
try:
    if not os.path.exists(root):
        os.mkdir(root)
    if not os.path.exists(path):
        r=requests.get(url)
        with open(path,'wb')as f:
            f.write(r.content)
            f.close()
            print("文件保存成功")
    else:
        print("文件已存在")
except:
    print("爬取失败")
