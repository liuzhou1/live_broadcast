# 商城 腾讯云直播

推流需要打开 app模块权限配置的 LivePusher(直播推流)，不需要集成其他关于直播的的sdk

### 推流核心代码介绍
var secretdate= '********';   //这是需要在腾讯云获取直播的密钥

let date = Date.parse(new Date())/1000 + 21600;  //当前时间六个小时后过期的十进制的时间戳（可自己设置过期时间）

this.url = 'http://live.sigequanwangluokeji.com/live/'+this.live_id+'.flv?txSecret='+md5(secretdate+this.live_id+date.toString(16).toUpperCase())+'&txTime='+date.toString(16).toUpperCase();

 http://live.sigequanwangluokeji.com/live ：这是需要在腾讯云配置推流的地址，这里采用的是flv的视频格式
 
 date.toString(16).toUpperCase()；    直播链接过期时间戳，先转成16进制，然后把小写转成大写
 
 this.live_id 是直播的id(房间号)；
 
 txSecret 是由直播的密钥、直播的id、16进制直播链接过期时间戳通过MD5加密生成
 
 txTime 链接有效期
 
 直接通过LivePusher标签就可以推流成功
 
 
### 拉流核心代码介绍

this.url = 'http://pull.sigequanwangluokeji.com/live/'+this.live_id+'.flv';

这是需要在腾讯云配置拉流的地址，加上直播id，直接在video标签就可以拉到直播


