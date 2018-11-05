---
title: Android手机连接到LEAP企业无线网络
author: 摩摩诘
type: post
date: 2011-04-07T16:11:40+00:00
excerpt: 很多公司内部的无线网络会用到LEAP认证机制，需要通过输入用户名和密码来登陆到无线网络。Android虽然支持LEAP，但没有在图形界面中加入这一选项。要在Android设备上使用LEAP无线网络，有两种解决方案：手动修改无线配置文件；安装支持LEAP WiFi的第三方APP。
url: /articles/android-leap.html
views:
  - 12582
index_image:
  - https://www.digglife.net/wp-content/uploads/2011/04/android_wifi.png
bot_views:
  - 444
dsq_thread_id:
  - 278081754
duoshuo_thread_id:
  - 1154125469839262146
wp-syntax-cache-content:
  - |
    a:4:{i:1;s:911:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    4
    5
    6
    7
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #007800;">network</span>=<span style="color: #7a0874; font-weight: bold;">&#123;</span>
    	<span style="color: #007800;">ssid</span>=“无限网络名称“
    	<span style="color: #007800;">key_mgmt</span>=你的无线网络使用的加密方式
    	<span style="color: #007800;">eap</span>=LEAP
    	<span style="color: #007800;">identity</span>=“用户名“
    	<span style="color: #007800;">password</span>=“密码“
    <span style="color: #7a0874; font-weight: bold;">&#125;</span></pre></td></tr></table><p class="theCode" style="display:none;">network={
    	ssid=“无限网络名称“
    	key_mgmt=你的无线网络使用的加密方式
    	eap=LEAP
    	identity=“用户名“
    	password=“密码“
    }</p></div>
    ";i:2;s:1844:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    4
    5
    6
    7
    8
    9
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #666666; font-style: italic;"># key_mgmt: list of accepted authenticated key management protocols</span>
    <span style="color: #666666; font-style: italic;"># WPA-PSK = WPA pre-shared key (this requires 'psk' field)</span>
    <span style="color: #666666; font-style: italic;"># WPA-EAP = WPA using EAP authentication</span>
    <span style="color: #666666; font-style: italic;"># IEEE8021X = IEEE 802.1X using EAP authentication and (optionally) dynamically</span>
    <span style="color: #666666; font-style: italic;">#	generated WEP keys</span>
    <span style="color: #666666; font-style: italic;"># NONE = WPA is not used; plaintext or static WEP could be used</span>
    <span style="color: #666666; font-style: italic;"># WPA-PSK-SHA256 = Like WPA-PSK but using stronger SHA256-based algorithms</span>
    <span style="color: #666666; font-style: italic;"># WPA-EAP-SHA256 = Like WPA-EAP but using stronger SHA256-based algorithms</span>
    <span style="color: #666666; font-style: italic;"># If not set, this defaults to: WPA-PSK WPA-EAP</span></pre></td></tr></table><p class="theCode" style="display:none;"># key_mgmt: list of accepted authenticated key management protocols
    # WPA-PSK = WPA pre-shared key (this requires 'psk' field)
    # WPA-EAP = WPA using EAP authentication
    # IEEE8021X = IEEE 802.1X using EAP authentication and (optionally) dynamically
    #	generated WEP keys
    # NONE = WPA is not used; plaintext or static WEP could be used
    # WPA-PSK-SHA256 = Like WPA-PSK but using stronger SHA256-based algorithms
    # WPA-EAP-SHA256 = Like WPA-EAP but using stronger SHA256-based algorithms
    # If not set, this defaults to: WPA-PSK WPA-EAP</p></div>
    ";i:3;s:860:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    4
    5
    6
    7
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #007800;">network</span>=<span style="color: #7a0874; font-weight: bold;">&#123;</span>
    	<span style="color: #007800;">ssid</span>=“digglife“
    	<span style="color: #007800;">key_mgmt</span>=WPA-EAP
    	<span style="color: #007800;">eap</span>=LEAP
    	<span style="color: #007800;">identity</span>=“momojie“
    	<span style="color: #007800;">password</span>=“<span style="color: #000000;">123456</span>“
    <span style="color: #7a0874; font-weight: bold;">&#125;</span></pre></td></tr></table><p class="theCode" style="display:none;">network={
    	ssid=“digglife“
    	key_mgmt=WPA-EAP
    	eap=LEAP
    	identity=“momojie“
    	password=“123456“
    }</p></div>
    ";i:4;s:621:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #660033;">-rw-rw----</span>    <span style="color: #000000;">1</span> system   wifi           <span style="color: #000000;">444</span> Apr  <span style="color: #000000;">7</span> <span style="color: #000000;">19</span>:<span style="color: #000000;">49</span> wpa_supplicant.conf</pre></td></tr></table><p class="theCode" style="display:none;">-rw-rw----    1 system   wifi           444 Apr  7 19:49 wpa_supplicant.conf</p></div>
    ";}
categories:
  - 掌上设备
tags:
  - android
  - google
  - LEAP
  - wifi
  - 手机
  - 无线网络

---
很多公司内部的无线网络会用到[LEAP认证机制][1]，需要通过输入用户名和密码来登陆到无线网络。如果你使用的是iOS设备，系统只会会提示你输入用户名和密码，你完全可以不必理会和无限网络技术相关的任何东西，而很遗憾的是，如果你手头上是一个Android设备，当你选择公司WiFi的时候系统弹出框会有几个项目需要自行选择，其中并没有出现LEAP字样（会有PEAP，EAP-TLS等），所以即便输入了用户名和密码也无法登陆。

事实上，Android本身是支持LEAP的，只是没有在图形界面中加入这一选项。这个问题早在2009年初就有人[在Android的Google Project讨论区提出][2]，跟帖很多，但是似乎并没有引起Android团队足够的重视，据我所知，直到Android 2.3 LEAP依然没有加入到WiFi的设定选项里，原因不明。

解决方案有两个：

  1. 手动修改wpa_supplicant配置文件，加入LEAP无线网络配置信息
  2. 安装第三方APP

### 方案一：手动修改wpa_supplicant配置文件，要 Root 权限

Android将所有连接过的WiFi热点信息都保存在/data/misc/wifi/wpa_supplicant.conf这个配置文件下，包括SSID，加密方式，WiFi密码等等，所以我们只要手动加入LEAP无线网络的完整信息，然后重启WiFi，系统就会重新获取配置文件中的信息，我们就能够登入新加入的LEAP无线网络了。

网上有[wpa_supplicant.conf的完整说明文件和范例][3]，大家可以参考。关于LEAP无线网络的范例如下：

<pre lang="bash" line="1">network={
	ssid=“无限网络名称“
	key_mgmt=你的无线网络使用的加密方式
	eap=LEAP
	identity=“用户名“
	password=“密码“
}
</pre>

关于key_mgmt，如果不设置，默认为最常见的WPA-PSK WPA-EAP。具体列表如下：

<pre lang="bash" line="1"># key_mgmt: list of accepted authenticated key management protocols
# WPA-PSK = WPA pre-shared key (this requires 'psk' field)
# WPA-EAP = WPA using EAP authentication
# IEEE8021X = IEEE 802.1X using EAP authentication and (optionally) dynamically
#	generated WEP keys
# NONE = WPA is not used; plaintext or static WEP could be used
# WPA-PSK-SHA256 = Like WPA-PSK but using stronger SHA256-based algorithms
# WPA-EAP-SHA256 = Like WPA-EAP but using stronger SHA256-based algorithms
# If not set, this defaults to: WPA-PSK WPA-EAP
</pre>

所以，对于一个SSID为digglife，使用WPA-EAP加密的LEAP无线网络，我们以用户名momojie和密码123456登陆，可以写成下面这样：

<pre lang="bash" line="1">network={
	ssid=“digglife“
	key_mgmt=WPA-EAP
	eap=LEAP
	identity=“momojie“
	password=“123456“
}
</pre>

将以上几行添加到wpa_supplicant.conf文件中即可。至于修改方法，我想就不必赘述了，用惯终端（或命令提示符）+ADB interface的朋友应该很熟悉。不习惯命令行的利用Root Explorer修改也可以。

注意，如果你在本地修改后上传到手机端，注意最后修改一下文件的权限、文件Owner和Group，否则在机器重启之后，系统可能无法读写这个配置文件，导致WiFi会提示错误。原始文件的权限设定如下：

<pre lang="bash" line="1">-rw-rw----    1 system   wifi           444 Apr  7 19:49 wpa_supplicant.conf
</pre>

### 方案二，安装第三方WiFi配置APP

下面介绍的这些APP只是将以上步骤UI化了而已，原理都是一致的，另外也不需要Root权限。

  1. [Full WiFi][4]
支持LEAP WiFi, PEAP, TKIP, CCMP等等，设定选项也很全面。

<img title="full-wifi" src="https://www.digglife.net/wp-content/uploads/2011/04/full-wifi.png" alt="支持配置 LEAP 无线网络的 Android 应用 Full WiFi" width="320" height="480" />

  2. [LEAP WiFi Free][5]
只针对LEAP WiFi的Android App，设定简单，输入SSID、用户名和密码，保存之后就可以在系统的WiFi设置里连接了。

<img title="leap-wifi-free" src="https://www.digglife.net/wp-content/uploads/2011/04/leap-wifi-free.png" alt="支持 LEAP 无线网络的 Android 应用 LEAP WiFi Free" width="320" height="480" /></ol> 

如果你手机已经获得Root权限，我还是建议使用第一种方法，不安装APP就能解决，何乐而不为？

 [1]: http://zh.wikipedia.org/zh/EAP
 [2]: http://code.google.com/p/android/issues/detail?id=1871
 [3]: http://hostap.epitest.fi/gitweb/gitweb.cgi?p=hostap.git;a=blob_plain;f=wpa_supplicant/wpa_supplicant.conf
 [4]: https://market.android.com/details?id=com.sharkmob.FullWifi
 [5]: https://market.android.com/details?id=com.oneguyinabasement.leapwifi
