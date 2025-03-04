# you2php-heroku

## YouTube 镜像网站, 实现免翻墙访问.
点击使用: https://bot-yt-test.herokuapp.com/<br>

### 本 Fork 更新
3/22/2019<br>
1. 更新了文件中的描述 PHP 版本.<br>
2. 去掉了密码验证, 方便观看.<br>
3. 更新了 config 设置.<br>

### 使用方法 v2.0 简易版
1. Fork 项目<br>
在当前页面点击右上角的 Fork 将项目拷贝至自己的 Github 账号下.<br>
2. 登录 heroku<br>
<a href="https://dashboard.heroku.com/apps">点我跳转</a><br>
3. 新建 app<br>
在 heroku 控制台页面点击 右上角的 New 新建一个 app, app 名称将作为网站域名<br>
<i>*使用敏感词汇将会触发 GFW 规则导致更快被封.</i><br>
4. 关联 Github<br>
创建完 app 后点击 app 进入 app 管理页面, 然后点击 Deploy(默认创建后跳转到这个页面).<br>
点击页面中的 GitHub/Connect to Github, 会要求你登录 Github, 请登录刚刚 Fork 项目的 Github账号.<br>
5. 部署<br>
当前页面将会显示你关联的 Github 账号, 在 Search for a repository to connect to 选项中输入 you2php-heroku
并点击 Searh, 选择 repo 点击 Connect, 连接完成后, 在最下方点击 Deploy Branch 完成部署.<br>
6. 注意事项<br>
```
1. 域名(app name)起敏感词汇将更容易被封.
2. 强烈建议启用密码保护, 教程见下方"其他建议".
3. 强烈建议使用自己的 API KEY 部署, 教程见下方"其他建议".
3. 越少人用, 越不容易被封.
4. 可能会因各种原因导致 app 被封(DNS 污染), 这时候换一个 URL 地址(app name)重新部署即可.
5. heroku 会定期停用对低版本的 PHP 的支持, 这个时候需要你根据错误提示, 修改 composer.lock 和 composer.json 中的描述.
```

### 自定义网站配置
修改 web/config 文件.<br>
```
<?php
$gl=(isset($_COOKIE['gl']) && $_COOKIE['gl'])?$_COOKIE['gl']:'US';
define('ROOT_PART', Root_part());
define('APIKEY', '你的 APIKEY');
define('GJ_CODE', $gl);
define('SITE_NAME', '你的网站名');
define('TITLENAME', '你的网站title');
define('EN2DEKEY', '一个随机字符串, 用于加密');
define('EMAIL', '你的邮箱, 用于处理版权纠纷');
?>
```

### 其他建议: <br>
1. 建议使用自己的 Google API Key 防止网站达到每日请求上限.<br>
2. 建议设置密码, GFW "似乎"加大了对 You2Php 的检测力度, 建议使用密码保护.<br>

以上均可以参考这篇教程: https://you2php.github.io/doc/ <br>
<i>*本文中所述网站可能存在被墙无法访问的情况, 请使用代理, 如果没有代理, 可以使用 <a href="https://gogogo-google.herokuapp.com/">网页代理</a>, 此网页代理能代理大多数网站, 在输入框中输入无法访问的网站即可.</i><br>
