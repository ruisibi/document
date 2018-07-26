# 扩展BI系统数据库导入功能

睿思BI系统目前支持从oracle/mysql/sqlserver/db2/hive/kylin/postgresql等数据库导入数据到BI系统中。用户也可以基于BI系统接口扩展对数据库的支持，操作过程如下：

1.创建数据库支持类并实现 com.ruisi.ext.engine.dao.DatabaseHelper 接口。

实例代码：

```java
package com.ruisi.ext.engine.dao;

import com.ruisi.ext.engine.view.context.grid.PageInfo;

public class PostgresqlHelperImpl implements DatabaseHelper {

    @Override
    public String getDatabaseType() {
        return "postgresql";
    }

    @Override
    public String getClazz() {
        return "org.postgresql.Driver";
    }

    @Override
    public String getQueryPageSql(String sql, PageInfo page) {
        String rsql = "select * from ( "+sql+" ) tt limit "+page.getPagesize() +" offset " + (page.getCurtpage() * page.getPagesize());
        return rsql;
    }


}
```

2.在 ext-config.xml文件中增加数据库的配置，如下:

```
<db type="postgresql" class="com.ruisi.ext.engine.dao.PostgresqlHelperImpl"/>
```

3.修**改数据库导入**页面，添加新的导入数据库。

![](/assets/import044.png)

