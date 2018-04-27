# 数据权限（接口模式）

数据权限表示用户能访问哪些数据，不能访问哪些数据。通过实现com.ruisi.vdop.service.frame.DataControlInterface 接口来控制数据权限。

通过用户所属组织机构控制权限示例：

```java
/**
* 通过实现DataControlInterface 接口实现数据权限控制。
* 此接口在系统每次查询中都会调用，接口返回数据权限过滤的SQL片段。
* @author zys
* @date 2015-2-20
*/
public class DataControlImp implements DataControlInterface {
/**
* @param u 会话中保存的用户信息
* @param master 此次查询中使用的主表的名称
*/
 public String process(User u, String master) {
    int lvl = u.getDeptLvl();
    if(lvl == 1){
        return " and " +  "lv3_id = '"+u.getDeptId()+"' " ;
    }else if(lvl == 2){
        return " and " + "lv2_id = '"+u.getDeptId()+"' " ;
    }else if(lvl == 3){
        return " and " + "dept_id = '"+u.getDeptId()+"' " ;
    }
    return "";
    }
}
```

然后在 applicationContext-persistence.xml 中注入您创建的类（替换以前的系统默认类）：

```java
<!-- 数据权限bean -->
<bean class="com.ruisitech.ext.service.DataControlImpl" name="dataControl"></bean>
```



