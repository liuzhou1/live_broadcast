#live_broadcast

var secretdate= '********';   //这是需要在腾讯云获取直播的密钥
			let date = Date.parse(new Date())/1000 + 21600;
			 //这是需要在腾讯云配置推流的地址，这里采用的是flv的视频格式
			this.url = 'http://live.sigequanwangluokeji.com/live/'+this.live_id+'.flv?txSecret='+md5(secretdate+this.live_id+date.toString(16).toUpperCase())+'&txTime='+date.toString(16).toUpperCase();

需要打开 app模块权限配置的 LivePusher(直播推流)和 Speech(语音输入) 和 VideoPlayer(视频播放)
