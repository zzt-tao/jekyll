# 输出
用 `{{}}` 进行输出，如：
```
{{ age }}
{{ page.hehe }}
{{ '么么哒' }}
```

# 过滤器
对输出内容进行过滤。
## 格式
```
{{page.zhaiyao | truncate:5}}
```

## 常见的过滤器
- truncate - 截取指定长度的字符串，第2个参数追加到字符串的尾部  {{ 'foobarfoobar' | truncate: 5, '.' }} # => 'foob.'
- strip_html - 删除 HTML 标签  {{ '<a href="">123</a>' | strip_html }} => 123
- 请参考： http://ju.outofmemory.cn/entry/149459
- 百度： jekyll语法 -> 第一条

# 全局变量
- page 代表当前页面，可以获取当前页面中定义的数据
- site 用于获取 `_config.yml` 配置文件中的数据
- content 用在模板文件中，代表子节点的内容
- paginator 获取分页的内容


# 目录结构
- _config.yml 文件，配置文件，在这个文件中配置的内容可以通过`site`全局变量获取

# 提取公共部分
1. include 包含方式
> 1. 用`{% include 文件路径 %}` 包含文件，记住头部要加6个-
> 2. 在文件夹下新建_includes文件夹，文件夹中存放公共文件

2. layout 布局的方式
> 1. 在为你工作根目录中新建_layouts文件夹
> 2. 在_layouts文件夹中创建一个模板文件，在模板文件中可以使用文件中的变量，还可以使用{{content}}来显示文件的其他内容