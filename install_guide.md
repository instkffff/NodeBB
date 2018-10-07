## Alliance forums

**nodebb联盟论坛安装方法**


1.部署nodejs环境和mangodb数据库

2.安装nginx作为端口转发

3.安装jre，jdk支持和最新版solr

4.下载nodebb主体从我的分支
	
* git clone https://github.com/instkffff/NodeBB.git
* ./nodebb setup (会有安装向导)
* 参考config.json.example  修改config.json (主要是socket.io设置，否则会报错，url设置与eveonline auth的callback地址一致)
* ./nodebb build
* ./nodebb start
  
5.根据我的插件列表截图，安装插件(未启用的可以卸载或不安装)

6.有2个插件需要使用我的分支版本(重要)
	
* https://github.com/instkffff/nodebb-theme-persona
* https://github.com/instkffff/nodebb-plugin-sso-eveonline
    
7.调试好以上包括ssl加密之后(hsts也可以配置一下，更好的chrome支持)，使用eve账号授权，然后使用默认设置时候的账号将其设置为管理员，并禁用其它注册登录方式。(论坛先切到中文模式)
	
* ACP --> 设置 --> 用户 --> 验证：允许本地登录：禁用
* ACP --> 设置 --> 用户 --> 用户注册：注册方式：禁用注册

8.设置论坛版块及member权限，由于eve-sso插件略复杂，我并没有制作alliance mapping功能，于是需要逐个公司填入mapping来获取member权限，非指定公司则获取register-user权限(不算老外70左右公司吧)。

9.由于论坛版块设定可以复制，所以先设定好几个模板版块，然后新建版块从模板版块复制权限即可(版块部署完毕后，我会根据最后版块分区，制作eve特色的图标进行上传)。

10.设定联盟管理组(联盟管理人员)，并邀请权限，及让这些人登录论坛确认。

11.设置各个主版块和子版块版主，作为帖子的管理者(修改，删除，移动标记问题已解决等操作)。

12.我将会保留我服务器的nodebb论坛作为测试环境并开放ssh给it组，来为正式部署做测试和完善，你们也可以在自家电脑本地进行部署测试(基本没有平台问题)。

13.后期继续完善主题(特色化)，及对使用中出现的问题进行解决。
