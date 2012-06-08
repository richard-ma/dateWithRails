===============================================================================
Rails速度
===============================================================================

这里的Blog并不是功能很完善的，如果你愿意，可以作为一个Blog。但它还缺少很多功能，现阶段只能做简单的CRUD操作

Step1 生成所有Blog需要的代码
===============================================================================
*$ rails generate scaffold Blog title:string author:string content:string*

这样，Rails会为你生成所有需要的代码。这个命令实际上是让Rails自动生成一个MVC的体系，Controller，Model和View都是以Blog命名的。

这些代码其实是分成几个部分分别生成的，我们来看一看。

第一部分叫active_record，主要是Model部分代码

* /db/migrate/xxxxxx_create_blogs.rb 创建Blog对应的数据库表
* /app/models/blog.rb Blog类
* /test/unit/blog_test.rb 对Blog类的单元测试
* /test/fixtures/blogs.yml 测试用数据

第二部分是Route

* resources :blogs 在/config/routes.rb中添加访问Blog相关页面的URL

第三部分是scaffold_controller，主要是Controller和View部分代码

* /app/controllers/blogs_controller.rb
* /app/views/blogs
* /app/views/blogs/index.html.erb
* /app/views/blogs/edit.html.erb
* /app/views/blogs/show.html.erb
* /app/views/blogs/new.html.erb
* /app/views/blogs/_form.html.erb
* /test/functional/blogs_controller_test.rb
* /app/helpers/blogs_helper.rb
* /app/unit/helpers/blogs_helper_test.rb

第四部分是最后一个部分assets，主要是Javascript和CSS等静态文件

* /app/assets/javascripts/blogs.js.coffee
* /app/assets/stylesheets/blogs.css.scss
