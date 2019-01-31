项目介绍
===
本项目基于Python,出生于春运期间，来自于一个抢不到票又不愿意找黄牛的执念。针对MTR高铁购票网站，破解验证码，刷新余票，一旦出现余票立刻抢座并且邮件通知（尽管验证码成功率只有60%）（但是平均十次就能成功六次了呢！）（成功率低的原因是因为不想花钱去打码，只能自己手动生成和网站尽可能一样的验证码，因此训练库和实际验证码仍有一定差别）（虽然看起来很厉害但我还是没有票）

实现方法
===
验证码破解 参考项目 [基于卷积神经网络的验证码识别](https://github.com/nickliqian/cnn_captcha)  
Python 操作网页 依赖模块  
        pip3 install selenium tensorflow==1.7.0 flask==1.0.2 requests==2.19.1 Pillow==4.3.0 matplotlib==2.1.0 easydict==1.8  
邮件发送 注意收件箱及发件箱均需开启 SMTP

参数配置
===

buyticket.py文件
---

  本项目针对郑州东--香港西九龙，若需要改变出发/到达站点，相应XPATH也需改变。具体可看文件内注释  
  isElementExist中定义的Xpath也需改变，见下图标红区域获取Xpath  
  ![](https://github.com/yayachipi/I-will-have-ticket/blob/master/image/githun.png)
  不同屏幕不同分辨率可能会需要配置不同的数据  
  运行buyticket文件后获取screenshot.png文件，用WIN自带的画图软件打开，光标放置验证码图片的左上角及右下角得到图片起始坐标。  
  根据记录的坐标，改变如下参数：    
  rangle = (int(x1), int(y1), int(x2),int(y2))  
  
emailto_u.py文件
---
根据注释标注填写邮箱就可以了

使用方法
===
        1.打开 recognize_api.py 开启本地接口  
        2.打开buyticket.py文件运行  
        3.完成，等待邮件通知  

写在最后
===
完成的很匆忙，很多细节可能没有顾及到，需要使用而又有疑惑不知如何操作的请私信我，包教包会  
Python算是新手，逻辑思维还需加强，各位对此项目有更好的建议请不吝赐教
