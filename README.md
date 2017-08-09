### 关联数据能力指标

这是一个后台知识库，用来生成关联数据能力指标的[文档网站](https://dcmi.github.io/ldci/)。该网站还支持通过众包的方式来维护这些指标。

#### 编辑JSON的主文档

根据[LDCI网站所描述的过程](https://dcmi.github.io/ldci/process/)，当一组修改被通过后, 拥有该知识库读写权限的人应该编辑[JSON主文档](https://github.com/dcmi/ldci/blob/master/docs/D2695955.json)。编辑方法如下所示：

* 进入网站http://rdf.tools => _ASN_ => _Configure_ => _Load ASN File_ => _choose existing file_ => 点击 [D2695955.json](https://github.com/dcmi/ldci/blob/master/docs/D2695955.json).
    *  如果JSON文档解析正确的话，编辑器会显示为绿色。
    *  _描述_ 表格: 关于指标的元数据。
    *  _创建_ 表格: 在此处编辑:
        * 点击右侧的空白处，左侧会自动填充相应的值.
        * 可以使用鼠标移动右边的内容来改变项目的顺序。
        * 可以通过点击主题，选择_Add @@@_来增加能力。
        * 点击 _Submit_进行保存。
    * 完成编辑后，按 _Submit_ => _Download_ => _Download RDF_ => _Save_的顺序提交保存。
        * RDF返回相同的文件名。
        * 使用此文件替换[JSON主文档](https://github.com/dcmi/ldci/blob/master/docs/D2695955.json).
        * 提交和推送。

#### Submit the master JSON file to ASN and WordPress

@@@ pending clarification with Joseph (for ASN) and the WordPress team

#### Generate a Markdown file from the master JSON file

* Run [D2695955_to_md.py](https://github.com/dcmi/ldci/blob/master/docs/D2695955_to_md.py) using Python 3 as shown in [Makefile](https://github.com/dcmi/ldci/blob/master/docs/Makefile).  This will over-write the existing file, [D2695955.md](https://github.com/dcmi/ldci/blob/master/docs/D2695955.md).  
* Commit and push.

#### Build the website using MkDocs

* Install [mkdocs](http://mkdocs.org) on your machine (see [installation instructions](http://www.mkdocs.org/#installation).
* Run the command `mkdocs gh-deploy` (or use [deploy.sh](https://github.com/dcmi/ldci/blob/master/deploy.sh)).  
    * This command creates (or refreshes) the website at [https://dcmi.github.io/ldci/](https://dcmi.github.io/ldci/).  
    * The command must be run from the root directory of this repo.  
    * Behind the scenes, `mkdocs gh-deploy` builds HTML docs from the Markdown sources, uses the `ghp-import` tool to commit them to the `gh-pages` branch, and pushes the `gh-pages` branch to GitHub.

