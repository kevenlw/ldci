### 关联数据能力指标

这是一个后台知识库，用来生成关联数据能力指标的[文档网站](https://dcmi.github.io/ldci/)。该网站还支持通过众包的方式来维护这些指标。

#### 编辑JSON的主文档

根据[LDCI网站所描述的过程](https://dcmi.github.io/ldci/process/)，当一组修改被通过后, 拥有该知识库读写权限的人应该编辑[JSON主文档](https://github.com/dcmi/ldci/blob/master/docs/D2695955.json)。编辑方法如下所示：

* 进入 http://rdf.tools => _ASN_ => _Configure_ => _Load ASN File_ => _Choose existing file_ => 点击 [D2695955.json](https://github.com/dcmi/ldci/blob/master/docs/D2695955.json).  
    * The editor displays green if the JSON file has parsed correctly.
    * _Describe_ tab: metadata about the index.
    * _Create_ tab: make edits here:
        * 点击右侧的空白处，左侧会自动填充相应的值.
        * 可以使用鼠标移动右边的内容来改变项目的顺序.
        * A competency can be added by clicking on a topic and selecting _Add @@@_.
        * Save work with _Submit_.
    * When the edits are done, press _Submit_ => _Download_ => _Download RDF_ => _Save_
        * RDF comes back out with the same filename.
        * Use this file to replace the [master JSON file](https://github.com/dcmi/ldci/blob/master/docs/D2695955.json).
        * Commit and push.

####  向ASN and WordPress提交JSON主文档

@@@ 使用Joseph (for ASN) 和the WordPress team进行说明.

#### 从JSON主文档生成一个Markdown文档

* 使用[Makefile](https://github.com/dcmi/ldci/blob/master/docs/Makefile)中所示的Python 3来运行[D2695955_to_md.py](https://github.com/dcmi/ldci/blob/master/docs/D2695955_to_md.py).  这将会改写现有的文档, [D2695955.md](https://github.com/dcmi/ldci/blob/master/docs/D2695955.md).  
* 提交和推送

#### 使用MkDocs来创建网站

* 安装[mkdocs](http://mkdocs.org) 到本机(参见 [安装指南](http://www.mkdocs.org/#installation).
* 运行命令 `mkdocs gh-deploy` (或使用[deploy.sh](https://github.com/dcmi/ldci/blob/master/deploy.sh)).   
    * This command creates (or refreshes) the website at [https://dcmi.github.io/ldci/](https://dcmi.github.io/ldci/). 
    * The command must be run from the root directory of this repo. 
    * Behind the scenes, `mkdocs gh-deploy` builds HTML docs from the Markdown sources, uses the `ghp-import` tool to commit them to the `gh-pages` branch, and pushes the `gh-pages` branch to GitHub.

