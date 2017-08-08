### 关联数据能力指标

这是一个后台知识库，用来生成关联数据能力指标的[文档网站](https://dcmi.github.io/ldci/)。该网站还支持通过众包的方式来维护这些指标。

#### 编辑JSON的主文档

根据[LDCI网站所描述的过程](https://dcmi.github.io/ldci/process/)，当一组修改被通过后, 拥有该知识库读写权限的人应该编辑[JSON主文档](https://github.com/dcmi/ldci/blob/master/docs/D2695955.json)。编辑方法如下所示：

* Go to http://rdf.tools => _ASN_ => _Configure_ => _Load ASN File_ => _Choose existing file_ => click on [D2695955.json](https://github.com/dcmi/ldci/blob/master/docs/D2695955.json).  
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

