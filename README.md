## 简述
一直想弄个短网址程序，看了眼这个项目很符合我的口味，但是有很多地方不太人性化

花了点时间边google边写，修修补补改出了这个版本

我也不是很会html和php，代码有什么地方很蠢的话请见谅

## 简介
Myurl 基于php+mysql实现的网址缩短服务，程序主要靠api.php 生成，前台是个静态页面，自己也可以进行修改美化

前台使用的乐视短网址的模板，内容已经本地化，看起来很简单

原作者的发布页面：http://www.aeink.com/myurl.html

在线真实网站演示：https://dlj.li
## 安装说明
1. 将程序上传至网站根目录，

2. 将install.sql上传至数据库

3. 修改config.php 数据库配置

4. nginx添加伪静态规则

5. 将index.html中所有的example.com修改为自己的网址
    
## NGINX伪静态

    location / {
            index index.php index.html;
            if (!-e $request_filename)
            {
                    rewrite ^/(.+)$ /do.php?uid=$1 last;
            }
    }

## 问题交流（原作者）

    优启梦官方交流群 463631294
    AE博客地址 www.aeink.com
    本程序为AE博客原创，由TNTcraftHIM修改

## 更新日志
	Myurl 1.4：
	1.本地化所有文件
	2.美化了界面
	3.添加了一键复制网址功能与各种实时反馈

	Myurl 1.3：
	1.取消防洪接口
	2.增加报毒检测接口
	3.修复首页异常提示
	
    Myurl 1.2：
    1.修复数据重复问题
    2.API空数据处理方式
    3.整合优启梦防洪(需要程序支持http://www.aeink.com/469.html)
    4.PHP7.0版本支持
    5.增加传入值判断
    6.增加txt输出方式
    7.增加GET|POST双支持

    Myurl 1.1：
    1.增加域名报毒使用接口进行跳转
    2.修复短网址访问404问题
    3.更新防屏蔽检测库

    Myurl 1.0
    1.长网址进行缩短功能
    2.API接口 返回JSON数据
    3.采用Mysql连接方式
