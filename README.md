# 2022最新v2ray和xray上cdn(cloudflare)教程记录

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

 ![image](https://user-images.githubusercontent.com/74105070/164357101-2cc80bed-447e-437f-a024-61cfb7836854.png)

**（以上是在cloudflare的流程步骤，这里代理先关闭，因为还要申请证书，所以先关闭cloudflare代理伪装域名）**

* **2：选择你选择的搭梯子类型；这里我选择：安装Xray-VLESS+WS+TLS(推荐)(可过支持WebSocket的CDN)，这里需要选择支持上cdn的协议。（如下图所示）**




