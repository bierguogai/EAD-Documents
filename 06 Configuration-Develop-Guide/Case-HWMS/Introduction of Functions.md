##固废功能简介
  这仅仅是作为一个示例，功能也仅仅是截取了固废管理系统的一个方面。包含四个方面，他们是固废分类、固废名称、内部管理分组、报批分组，如**图1**。四个类别我们均可以在页面中实现CRUD。对于四者的关系，可以笼统的概括为固废名称是中心，其他三个都是作为字典为其提供数据，具体四者所包含的属性以及关系如**图2**所示  
![PNG](..\images\hwms\1.png)
<div align=center><p>图1 示例四个功能</p></div>  

![PNG](..\images\hwms\2.png)
<div align=center><p>图2 功能包含字段及关系</p></div>  

>注意，在图2中，（全）代表在列表以及详细页面都显示，（详）代表只在详细页面显示，（藏）代表在列表以及详细页面都不显示，（虚）代表虚拟属性。红色代表表单中会出现。    

