# [webssh](https://github.com/amclubs/webssh)
webssh 页面工具，解决ssh直接可以通过浏览器连接，增加生成sshlink功能，方便收藏，下次使用不需要输入密码。

#
▶️ **新人[YouTube](https://youtube.com/@am_clubs?sub_confirmation=1)** 需要您的支持，请务必帮我**点赞**、**关注**、**打开小铃铛**，***十分感谢！！！*** ✅
</br>🎁请 **follow** 我的[GitHub](https://github.com/amclubs)、给我所有项目一个 **Star** 星星（拜托了）！你的支持是我不断前进的动力！ 💖
</br>✅**解锁更多技能** [加入TG群【am_clubs】](https://t.me/am_clubs)、[YouTube频道【@am_clubs】](https://youtube.com/@am_clubs?sub_confirmation=1)、[【博客(国内)】](https://amclubss.com)、[【博客(国际)】](https://amclubs.blogspot.com) 
</br>✅点击观看教程[CLoudflare免费节点](https://www.youtube.com/playlist?list=PLGVQi7TjHKXbrY0Pk8gm3T7m8MZ-InquF) | [VPS搭建节点](https://www.youtube.com/playlist?list=PLGVQi7TjHKXaVlrHP9Du61CaEThYCQaiY) | [获取免费域名](https://www.youtube.com/playlist?list=PLGVQi7TjHKXZGODTvB8DEervrmHANQ1AR) | [免费VPN](https://www.youtube.com/playlist?list=PLGVQi7TjHKXY7V2JF-ShRSVwGANlZULdk) | [IPTV源](https://www.youtube.com/playlist?list=PLGVQi7TjHKXbkozDYVsDRJhbnNaEOC76w) | [Mac和Win工具](https://www.youtube.com/playlist?list=PLGVQi7TjHKXYBWu65yP8E08HxAu9LbCWm) | [AI分享](https://www.youtube.com/playlist?list=PLGVQi7TjHKXaodkM-mS-2Nwggwc5wRjqY)


## 一、VPS部署方法
<details>
<summary>点击展开/收起</summary>

- 1、下载webssh安装包命令：
	```
	git clone https://github.com/amclubs/webssh
	```

- 2、**绑定Cloudflare域名生成证书**,并上传到服务器指定目录 <a href="https://youtu.be/cI36vtXuQrM">[点击观看视频教程]</a>
	```
	cd websssh
	```

- 3、安装webssh命令：

	**Python2** 安装webssh命令：
	```
	pip install webssh
	```

	**Python3** 安装webssh命令：
	```
	pip3 install webssh
	```

- 4、运行webssh命令 **(certfile/keyfile证书目录换成你服务器存储的目录和文件名称)**：

	**Python2** 运行webssh命令：
	```
	nohup python run.py --certfile='/root/cert/809098.pem' --keyfile='/root/cert/809098.key' --sslport=8443 > /dev/null 2>&1 &
	```

	**Python3** 运行webssh命令：
	```
	nohup python3 run.py --certfile='/root/cert/809098.pem' --keyfile='/root/cert/809098.key' --sslport=8443 > /dev/null 2>&1 &
	```

- 5、访问webssh：
	```
	https://域名:端口
	```

- 6、设置开机自动启动webssh **(WorkingDirectory/certfile/keyfile证书目录换成你服务器存储的目录和文件名称)**：
	1、写一个 service 文件 webssh.service
	```
	[Unit]
	Description=WebSSH Service
	After=network.target

	[Service]
	Type=simple
	WorkingDirectory=/root/webssh
	ExecStart=/usr/bin/python3 run.py --certfile='/root/cert/809098.pem' --keyfile='/root/cert/809098.key' --sslport=8443
	Restart=always
	User=root

	[Install]
	WantedBy=multi-user.target
	```

	2、让服务生效
	```
	systemctl daemon-reload
	systemctl enable webssh
	systemctl start webssh
	```

	3、管理服务
	查看状态
	```
	systemctl status webssh    
	```
	重启
	```
	systemctl restart webssh
	```
	停止
	```
	systemctl stop webssh
	```
</details>

## 二、 koyeb部署方法(计划中)

## 三、 fly.io部署方法(计划中)

## 四、 Serv00部署方法(计划中)

# 感谢
[crazypeace](https://github.com/crazypeace/huashengdun-webssh)

# 
<center>
<details><summary><strong> [点击展开] 赞赏支持 ~🧧</strong></summary>
*我非常感谢您的赞赏和支持，它们将极大地激励我继续创新，持续产生有价值的工作。*

- **USDT-TRC20:** `TWTxUyay6QJN3K4fs4kvJTT8Zfa2mWTwDD`
- **TRX-TRC20:** `TWTxUyay6QJN3K4fs4kvJTT8Zfa2mWTwDD`

<div align="center"> 
  <img src="https://github.com/user-attachments/assets/e6cdc42a-6374-4722-b833-601738f72196" width="200"></br> 
  TRC10/TRC20扫码支付 
</div> 
</details>
</center>

 #
 免责声明:
 - 1、该项目设计和开发仅供学习、研究和安全测试目的。请于下载后 24 小时内删除, 不得用作任何商业用途, 文字、数据及图片均有所属版权, 如转载须注明来源。
 - 2、使用本程序必循遵守部署服务器所在地区的法律、所在国家和用户所在国家的法律法规。对任何人或团体使用该项目时产生的任何后果由使用者承担。
 - 3、作者不对使用该项目可能引起的任何直接或间接损害负责。作者保留随时更新免责声明的权利，且不另行通知。