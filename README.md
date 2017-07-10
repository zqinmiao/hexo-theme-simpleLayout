# hexo-theme-simpleLayout
简单布局、简单配置、简简单单写文章

[在线预览](http://yayajiu.com/)

---

# 初始化一个Hexo项目，[参考](https://hexo.io/zh-cn/docs/setup.html)
    $ npm install -g hexo-cli
    $ hexo init zqinmiao.github.io
    $ npm install

### 以zqinmiao.github.io文件夹为例(下面提到的zqinmiao.github.io文件夹就是指Hexo的博客项目)

把zqinmiao.github.io(此文件夹一般是你对应的github仓库名称)目录下的source文件夹清空(清空的目的是把init时产生的文章清理了)

---

# 安装hexo-theme-simpleLayout
    $ git clone https://github.com/zqinmiao/hexo-theme-simpleLayout.git

先将文件夹hexo-theme-simpleLayout放到zqinmiao.github.io项目下的themes文件夹下
    $ cd hexo-theme-simpleLayout
    $ npm install

---

# 配置zqinmiao.github.io项目下的_config.yml文件

    # Hexo Configuration
    # Site
    #网站标题
    title: reahink
    #子标题
    subtitle:
    #网站描述
    description: 博客、blog、技术、读读、想想、写写
    #网站作者
    author: reahink
    #网站语言
    language: zh-CN
    #网站所在时区
    timezone: Asia/Shanghai

    # URL
    #-----------------------------------------
    ## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
    url: https://zqinmiao.github.io/
    root: /
    permalink: :year/:month/:title/
    permalink_defaults:

    # Directory
    #-----------------------------------------
    #资源文件夹，这个文件夹用来存放内容
    source_dir: source
    #公共文件夹，这个文件夹用于存放生成的站点文件
    public_dir: public
    #标签文件夹
    tag_dir: tags
    #归档文件夹
    archive_dir: archives
    #分类文件夹
    category_dir: categories
    #Include code 文件夹
    code_dir: downloads/code
    #国际化（i18n）文件夹
    i18n_dir: :lang
    #跳过指定文件的渲染，您可使用 glob 表达式来匹配路径
    skip_render:

    # Writing
    #-----------------------------------------
    #新文章的文件名称
    new_post_name: :title.md # File name of new posts
    #预设布局
    default_layout: post
    #把标题转换为 title case
    titlecase: false # Transform title into titlecase
    #在新标签中打开链接
    external_link: true # Open external links in new tab
    #把文件名称转换为 (1) 小写或 (2) 大写
    filename_case: 0
    #显示草稿
    render_drafts: false

    #启动 Asset 文件夹==>资源（Asset）代表 source 文件夹中除了文章以外的所有文件，例如图片、CSS、JS 文件等
    post_asset_folder: true

    #把链接改为与根目录的相对位址
    relative_link: false
    #显示未来的文章
    future: true

    #代码块的设置
    highlight:
      enable: true
      line_number: true
      auto_detect: false
      tab_replace:

    # Category & Tag
    #-----------------------------------------
    default_category: uncategorized
    category_map:
    tag_map:

    # Date / Time format
    #-----------------------------------------
    ## Hexo uses Moment.js to parse and display date
    ## You can customize the date format as defined in
    ## http://momentjs.com/docs/#/displaying/format/
    date_format: YYYY-MM-DD
    time_format: HH:mm:ss

    # Pagination
    #-----------------------------------------
    ## Set per_page to 0 to disable pagination
    #每页显示的文章量 (0 = 关闭分页功能)
    per_page: 10
    #分页目录
    pagination_dir: page

    # Extensions
    #-----------------------------------------
    ## Plugins: https://hexo.io/plugins/
    #RSS订阅
    plugin:
    - hexo-generator-feed

    ## Themes: https://hexo.io/themes/
    #-----------------------------------------
    theme: hexo-theme-simpleLayout

    # Deployment
    #-----------------------------------------
    ## Docs: https://hexo.io/docs/deployment.html
    deploy:
      type: git
      repo: git@github.com:zqinmiao/zqinmiao.github.io.git
      branch: master

将theme的值修改为：hexo-theme-simpleLayout，就可以使用hexo-theme-simpleLayout主题了
关于_config.yml中各项意思，参考[配置](https://hexo.io/zh-cn/docs/configuration.html)

---

# 进入themes ——> hexo-theme-simpleLayout文件夹，配置此文件夹下的_config.yml文件

    #hexo-theme-simpleLayout
    #--------------------------------------

    # Header
    #这是网站菜单栏，HOME、ABOUT、RSS对应菜单栏的名称，可以自行修改
    menu:
      HOME: /
      ABOUT: /about
      RSS: /atom.xml

    # Sidebar
    #这是网站侧边栏，Category、Tag、Archive对应侧边栏的名称，可以自行修改其对应的值
    widgets:
      Category: Category
      Tag: Tags
      Archive: Archive
      Tagcloud:
      Recent_Post:

    # Content
    #网站阅读更多的文字，可自行修改excerpt_link对应的值
    excerpt_link: 阅读全文

    #SNS
    #这是关于我页面社交网站的链接，依次分别是微博、github、zhihu，可自行修改对应链接
    social_media:
      weibo: http://weibo.com/abcde6789ooo/
      github: https://www.zhihu.com/people/reahink
      zhihu: https://github.com/zqinmiao

    #theme color
    #此部分暂不支持
    color:
      body_background:
      header_background:
      header_font:

    # 其他
    favicon: /favicon.ico
---

# 配置留言功能
在hexo-theme-simpleLayout目录下：

    hexo-theme-simpleLayout
        ├──src
        │   └──js
        │       ├─gitment.js

修改gitment.js：

    var gitment = new Gitment({
        owner: 'zqinmiao',//此处需修改
        repo: 'zqinmiao.github.io',//此处需修改
        oauth: {
            client_id: '30dead4389a232431a46',//此处需修改
            client_secret: '039e0c7f9a8303e2d01d66e150134d591d1e7703',//此处需修改
        },
    });
    gitment.render('comment-wrap');

"需要修改处"的参数如何获取，请参考[这里](https://imsun.net/posts/gitment-introduction/#more)

修改后需执行：

    $ gulp

---

# 配置ABOUT(关于我)
在zqinmiao.github.io项目下:

    ├──zqinmiao.github.io
    │      └──source
    │            ├─about

在about文件夹下建一个名为：index.md的markdown文件，文件内容为：

    ---
    title: about
    layout: about
    ---
    这里就可以使用markdown语法写关于我的东西了

---

# 配置网站在浏览器头部的小图标
把favicon.ico放在source目录下：

    hexo-theme-simpleLayout
        ├──source

---

# 如何设置自定义域名
[参考这里](http://yayajiu.com/2017/01/%E5%85%B3%E4%BA%8E%E4%BD%BF%E7%94%A8Hexo%E6%90%AD%E5%BB%BA%E5%8D%9A%E5%AE%A2%E7%9A%84%E4%B8%80%E4%BA%9B%E9%97%AE%E9%A2%98%E6%80%BB%E7%BB%93/#博客网址使用自定义域名)