# vue-admin-thinkphp 是基于vue-admin-template+thinkphp5的后台权限管理系统
## 视频演示
链接：[点我查看演示视频](http://demo.o8o8o8.com/vue/vueAdminTemplate/index.html)

## 目录介绍
1.vuestage  前端项目文件<br>
2.vueadmin  后端项目文件<br>
3.sql下载地址：https://pan.baidu.com/s/1_yFKpMJfmm-yURQb_RXNpw 密码：star后留下邮箱获取（防止伸手党）

## 如何使用
### 后端项目搭建
~~~
1.环境要求：php版本>=5.5 mysql版本>=5.5
2.拷贝vueadmin文件夹下的文件到你的网站服务器的根目录，或者将vueadmin设置为你的web根目录
3.vueadmin\vue_admin.sql导入到你的mysql数据库
4.配置vueadmin\application\database.php 数据库连接信息
5.启动WEB服务器
~~~
### 前端项目搭建
~~~
1.安装nodejs环境
2.cmd进入vuestage目录
3.npm install 初始化项目
4.配置vuestage\config\index.js  配置node服务器 host和port
5.开发环境下 配置 vuestage\config\dev.env.js BASE_API为API请求路径前缀
6.生产环境 配置 vuestage\config\dev.env.js
~~~

## 开发简易教程（大神绕道）
以管理员增删改查为例(已经成功运行项目基础上，上面已经介绍了怎么搭建，自行领悟)<br>
### 1.登录
  首先命令行进入vuestage目录，执行npm run dev运行客户端<br>
  并启动web服务器<br>
  进入后台界面登录界面<br>
  超级管理员账号密码默认为super  123456<br><br>
  ![图片](https://github.com/shenxingchao/vue-admin-thinkphp/blob/master/images/opt1.png?v=1)<br>
### 2.添加菜单路由配置
  将管理员作为二级菜单添加到权限管理菜单下 如下图<br><br>
  ![图片](https://github.com/shenxingchao/vue-admin-thinkphp/blob/master/images/opt2.png?v=1)<br>
  表单值介绍<br><br>
  ![图片](https://github.com/shenxingchao/vue-admin-thinkphp/blob/master/images/opt3.png?v=1)<br><br>
  依次添加  管理员列表、添加管理员、编辑管理员页面的路由配置<br>
  菜单资源配置就是有页面的路由 如添加页面，编辑页面，列表页面等，（不包括操作页面，如删除操作）<br>
  svg图标则是从 [iconfont](http://www.iconfont.cn) 上下载下来的，保存到vuestage\src\icons\svg\文件夹下，自己命名即可，这里命名为admin.svg<br>
  如下图<br><br>
  ![图片](https://github.com/shenxingchao/vue-admin-thinkphp/blob/master/images/svg.png?v=1)<br>
### 3.创建视图文件
  分别创建<br>
  admin.vue<br>
  admin_add.vue<br>
  admin_edit.vue<br>
  admin_lst.vue<br>
  创建前端视图页面<br><br>
  ![图片](https://github.com/shenxingchao/vue-admin-thinkphp/blob/master/images/opt4.png?v=1)<br>
  (需要注意的是必须创建admin.vue空视图页面,对应着就是左侧的菜单权限——管理员菜单)<br>
### 4.配置路由映射视图文件（重要）
  找到vuestage\src\router\map.js  路由映射文件<br>
  如下图配置<br><br>
  ![图片](https://github.com/shenxingchao/vue-admin-thinkphp/blob/master/images/routermap.png?v=1)<br>
### 5.创建后端api接口文件
  找到vuestage\src\api\permission\  新建admin.js<br>
  如下图<br><br>
  ![图片](https://github.com/shenxingchao/vue-admin-thinkphp/blob/master/images/api.png?v=1)<br>
### 6.控制增删改查数据库操作权限
  上面的只能是控制页面的显示，并不能控制后端请求权限,那么怎么办呢<br>
  重新打开我们的后台，添加权限资源如下图<br><br>
  ![图片](https://github.com/shenxingchao/vue-admin-thinkphp/blob/master/images/src.png?v=1)<br>
### 7.配置角色权限
  最后在角色列表中配置相关的视图可见权限和后台请求操作权限即可<br>
  如下图所示<br><br>
  ![图片](https://github.com/shenxingchao/vue-admin-thinkphp/blob/master/images/role.png?v=1)<br>
### 8.ps
以上可能有许多不完善的地方，欢迎提问和批评


