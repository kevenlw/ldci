### 关联数据能力指标

这是一个后台知识库，用来生成关联数据能力指标的[文档网站](https://dcmi.github.io/ldci/)。该网站还支持通过众包的方式来维护这些指标。

#### 编辑JSON的主文档

根据[LDCI网站所描述的过程](https://dcmi.github.io/ldci/process/)，当一组修改被通过后, 拥有该知识库读写权限的人应该编辑[JSON主文档](https://github.com/dcmi/ldci/blob/master/docs/D2695955.json)。编辑方法如下所示：

* 进入 http://rdf.tools => _ASN_ => _Configure_ => _Load ASN File_ => _Choose existing file_ => 点击 [D2695955.json](https://github.com/dcmi/ldci/blob/master/docs/D2695955.json).  
    * 如果JSON文档解析正确，编辑器会显示为绿色。
    * _描述_ 标签:关于指标的元数据。
    * _创建_ 标签:在此处进行编辑:
        * 点击右侧的空白处，左侧会自动填充相应的值。
        * 可以使用鼠标移动右边的内容来改变项目的顺序。
        * 可以通过点击主题，选择_Add @@@_来增加能力。
        * 点击_Submit_进行保存。
    * 完成编辑后，按  _Submit_ => _Download_ => _Download RDF_ => _Save_的顺序提交保存。
        * RDF返回相同的文件名。
        * 使用此文件替换[JSON主文档](https://github.com/dcmi/ldci/blob/master/docs/D2695955.json)。
        * 提交和推送。

####  向ASN and WordPress提交JSON主文档

@@@ 使用Joseph (for ASN) 和the WordPress team进行说明。

#### 从JSON主文档生成一个Markdown文档

* 使用[Makefile](https://github.com/dcmi/ldci/blob/master/docs/Makefile)中所示的Python 3来运行[D2695955_to_md.py](https://github.com/dcmi/ldci/blob/master/docs/D2695955_to_md.py)。这将会改写现有的文档, [D2695955.md](https://github.com/dcmi/ldci/blob/master/docs/D2695955.md)。  
* 提交和推送

#### 使用MkDocs来创建网站

* 安装[mkdocs](http://mkdocs.org) 到本机(参见 [安装指南](http://www.mkdocs.org/#installation)。
* 运行命令 `mkdocs gh-deploy` (或使用[deploy.sh](https://github.com/dcmi/ldci/blob/master/deploy.sh))。   
    * 此命令会创建或刷新此网站 [https://dcmi.github.io/ldci/](https://dcmi.github.io/ldci/)。 
    * 此命令必须在该知识库的根目录下运行。 
    * 在后台,`mkdocs gh-deploy` 通过Markdown创建HTML文档,使用`ghp-import`工具提交至`gh-pages`分库,然后推送`gh-pages`分库至GitHub。

