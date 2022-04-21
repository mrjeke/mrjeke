# 2022最新v2ray和xray上cdn(cloudflare)教程记录（宝塔环境搭配）

**注：理论所有协议只要支持cdn流量转发教程都适用**

**思路流程：**

* **1：先搭配好梯子，测试能不能翻墙；**
* **2：测试好梯子可以翻墙，后面才开始上cdn（cloudflare）。也就是说梯子和cdn是两个部分，并不相互影响。**

**（总结思路就是，搭建梯子过程中，同时搭配cdn（cloudflare））**

## **开始流程：**

* **1：选择注册一个新的梯子伪装域名，然后再域名注册商那里选择你那个域名的DNS解析修改成cloudflare给DNS解析（这一步很重要，如果你成功把伪装域名dns解析修改成cloudflare，再进去cloudflare个人中心域名那里会提示：域名有效的提示。而且每个域名注册商修改dns解析地方不一样，自己仔细找找，我这里用的是dynadot域名注册商）**
 ![image](https://user-images.githubusercontent.com/74105070/164357399-9627e98d-f731-40f7-8aea-d5d0422dcaca.png)

**（cloudflare给出DNS解析服务器）**
![image](https://user-images.githubusercontent.com/74105070/164356579-08beabfa-aefd-4c0d-8542-207c85857f8e.png)

**（在自己的域名注册商修改伪装域名为cloudflare给出DNS解析）**

 ![3a09b325f14bec897bbdc1f242d6d0d](https://user-images.githubusercontent.com/74105070/164356087-346ebe11-343c-433a-a502-b74a9f46fcaf.png)
 **（cloudflare会提示成功把伪装域名dns解析修改为cloudflare的dns解析）**
 
 ![image](https://user-images.githubusercontent.com/74105070/164357101-2cc80bed-447e-437f-a024-61cfb7836854.png)

**（以上是在cloudflare的流程步骤，这里代理先关闭，因为还要申请证书，所以先关闭cloudflare代理伪装域名（如果提前开启cdn代理伪装域名会导致证书无法申请！））**
* **2：完成上面cloudflare解析工作，开始申请伪装域名的证书，证书我建议选择腾讯云或者阿里云或者其他一年的免费证书也就是自定义证书，当然可以选择3个月有效期的Let's Encrypt证书，但是3个月时间太短了，而且到时候证书到期自带续签得关闭伪装域名的cdn代理，时间短还请频繁申请申请证书，所以建议索性申请一年时间有效期的证书**
* 
* **3：下面就是你选择的搭梯子类型；这里我选择：安装Xray-VLESS+WS+TLS(推荐)(可过支持WebSocket的CDN)，这里需要选择支持上cdn的协议。（如下图所示）**
![4f086bda4e79729d2bec18afdf80f14](https://user-images.githubusercontent.com/74105070/164358801-2f958bdd-b3a5-4dd5-83df-e25987fccd3b.png)

* **4：提前把申请的证书文件放到指定文件夹下，而且重命名（如下图所示）**
* ![image](https://user-images.githubusercontent.com/74105070/164359682-7671d0d3-cc7e-4685-b065-d05e19e7b66a.png)
* 
* **5：这时候进一步按照命令行安装，会出现如下图所示我们提前上传到文件夹的证书文件。**
![090dddaa7aab3d238705883881b83a3](https://user-images.githubusercontent.com/74105070/164359979-448f4860-50db-4bd1-b874-4d55b85a04cb.png)

* **6：下面就是脚本以及安装直至到成功安装梯子，安装完成之后到开测试梯子打开客户端填进去参数测试梯子是否成功。然后到cloudflare开始小云朵代理，过几分钟，cloudflare成功代理我们的伪装域名（如下图所示）**
![image](https://user-images.githubusercontent.com/74105070/164360836-d73c5f4a-d2e2-4798-9559-a8fc7540af3b.png)

* **7：到这里，梯子上cdn是基本完成，但是你会发现无法打开伪装网站，而且提示证书不受浏览器支持（可以翻墙，不影响梯子）这时候你需要还需要到cloudflare设置代理ssl/tls，把您的 SSL/TLS 加密模式为 完全（严格）**
* ![image](https://user-images.githubusercontent.com/74105070/164361448-000a7cd8-8862-47fd-b261-68cebf75b1d3.png)
* 
* **8：然后点击设置边缘证书，最低 TLS 版本仅允许来自支持所选 TLS 协议版本或更高版本的访问者的 HTTPS 连接为：TLS1.3版本（入下图所示）**
![image](https://user-images.githubusercontent.com/74105070/164361739-6912f416-1d83-4bd6-8511-06f84567beeb.png)

* **9：如果成功运行cdn cloudflare代理梯子域名，在概述那里会出现：通过 TLS 提供的流量（如下图所示） 否则可能没有成功代理cdn**
![image](https://user-images.githubusercontent.com/74105070/164362068-0c10afac-ec75-40fe-853a-c8a0e6a76f80.png)

* **10：至此，整个教程完成！**
* 
* @绝客博客

