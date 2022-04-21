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
* **3：下面就是你选择的搭梯子类型；这里我选择：安装Xray-VLESS+WS+TLS(推荐)(可过支持WebSocket的CDN)，这里需要选择支持上cdn的协议。（如下图所示）**
![4f086bda4e79729d2bec18afdf80f14](https://user-images.githubusercontent.com/74105070/164358801-2f958bdd-b3a5-4dd5-83df-e25987fccd3b.png)
* **4：提前把申请的证书文件放到指定文件夹下，而且重命名（如下图所示）**
* ![image](https://user-images.githubusercontent.com/74105070/164359682-7671d0d3-cc7e-4685-b065-d05e19e7b66a.png)
* **5：这时候进一步按照命令行安装，会出现如下图所示我们提前上传到文件夹的证书文件。 **
![090dddaa7aab3d238705883881b83a3](https://user-images.githubusercontent.com/74105070/164359979-448f4860-50db-4bd1-b874-4d55b85a04cb.png)



