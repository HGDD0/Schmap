# Schmap
A script used to generate citation graphs

前置需求：
1. 安装import部分所需的包
2. 安装对应的web driver用于使用 selenium3 进行浏览器控制 可以参考：http://www.testclass.net/selenium_python/selenium3-browser-driver 示例脚本中使用的是chrome，使用其他浏览器需改动代码

快速开始：
1. 从semantic scholar 中找到你感兴趣的大佬，其页面链接最后的一串数字即为其编号，修改代码中的 ini_id 为你感兴趣的作者编号（注意全文中有两处）
2. 在Author类中找到 driver = webdriver.Chrome('C:\Program Files (x86)\Google\Chrome\Application\chromedriver',options=opt) 将其路径修改为你安装web driver的路径
3. 找到 #进行多少轮搜索 for t in range(1,4): 修改为你想要的轮数，(1,2)即进行一轮，只产生一个节点，一般建议不做修改以取得网络规模和网速限制的balance

常见bug：
1. 运行爬虫的时候element not found ：多半是网络不好，到了设置的超时时间网页还没加载完
2. 运行关键词提取的时候提示次数不足： 当天次数用完了，改天再说，或者自己去https://www.textrazor.com/ 注册一个账号，替换代码开始的textrazor.api_key
