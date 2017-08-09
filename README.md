### 关联数据能力指标

这是一个后台知识库，用来生成关联数据能力指标的[文档网站](https://dcmi.github.io/ldci/)。该网站还支持通过众包的方式来维护这些指标。

#### 编辑JSON的主文档

根据[LDCI网站所描述的过程](https://dcmi.github.io/ldci/process/)，当一组修改被通过后, 拥有该知识库读写权限的人应该编辑[JSON主文档](https://github.com/dcmi/ldci/blob/master/docs/D2695955.json)。编辑方法如下所示：

* 进入 http://rdf.tools => _ASN_ => _Configure_ => _Load ASN File_ => _Choose existing file_ => 点击 [D2695955.json](https://github.com/dcmi/ldci/blob/master/docs/D2695955.json).  
    * The editor displays green if the JSON file has parsed correctly.
    * _Describe_ tab: metadata about the index.
    * _Create_ tab: make edits here:
        * Clicking on a node (on the right) will populate the corresponding values (on the left).
        * The order of items can be changed by moving things around, on the right, using the mouse.
        * A competency can be added by clicking on a topic and selecting _Add @@@_.
        * Save work with _Submit_.
    * When the edits are done, press _Submit_ => _Download_ => _Download RDF_ => _Save_
        * RDF comes back out with the same filename.
        * Use this file to replace the [master JSON file](https://github.com/dcmi/ldci/blob/master/docs/D2695955.json).
        * Commit and push.

####  向ASN and WordPress提交JSON主文档

@@@ pending clarification with Joseph (for ASN) and the WordPress team

#### 从JSON主文档生成一个Markdown文档

* 使用[Makefile](https://github.com/dcmi/ldci/blob/master/docs/Makefile)中所示的Python 3来运行[D2695955_to_md.py](https://github.com/dcmi/ldci/blob/master/docs/D2695955_to_md.py).  这将会改写现有的文档, [D2695955.md](https://github.com/dcmi/ldci/blob/master/docs/D2695955.md).  
* 提交和推送

#### 使用MkDocs来创建网站

* 安装[mkdocs](http://mkdocs.org) 到本机(参见 [安装指南](http://www.mkdocs.org/#installation).
* 运行命令 `mkdocs gh-deploy` (或使用[deploy.sh](https://github.com/dcmi/ldci/blob/master/deploy.sh)). 
    * 此命令会创建(或刷新) 此网站 [https://dcmi.github.io/ldci/](https://dcmi.github.io/ldci/).  
    * 此命令必须在该知识库的根目录下运行。
    * 在后台, `mkdocs gh-deploy` 通过Markdown创建HTML文档, 使用 `ghp-import` 工具提交至 `gh-pages` 分库, 推送 `gh-pages` 分库至GitHub.

