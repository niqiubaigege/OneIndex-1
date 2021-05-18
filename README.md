### 权限申请

	1、登录 https://portal.azure.com
	
	2、应用注册 - 新注册 - 填写应用名称 - 账户类型点选C - 重定向URI(即redirect_uri)选Web,值填写部署地址或本机http://localhost - 保存 client_id
	
	3、证书和密码 - 新客户端密码 - 设置有效期 - 保存 client_secret
	
	4、API权限 - 添加权限 - Microsoft Graph 权限 - 勾选 Files.Read、Files.ReadWrite、offline_access权限、保存
	
### 部署
	
	1、环境要求 php5.5+ & curl拓展开启
	
	2、目录 config/ 和 cache/ 可读可写
	
### Apache伪静态去除url中'/?/'

	```
	<IfModule mod_rewrite.c>
		RewriteEngine on
		RewriteBase /
		RewriteCond %{REQUEST_FILENAME} !-d
		RewriteCond %{REQUEST_FILENAME} !-f
		RewriteRule ^(.*)$ index.php/$1 [QSA,PT,L]
	</IfModule>
	```

### 后台管理员地址

	登录地址/admin,初始密码:oneindex
	
### 特殊文件

	1、加密当前目录:OneDrive中目标目录下添加.password文件，内容为密码
	
	2、目录页顶部添加说明页:OneDrive中目标目录下添加HEAD.md文件
	
### 重新安装
	
	1、后台管理-页面缓存-清楚所有缓存
	
	2、连接ftp删除/config下所有文件
