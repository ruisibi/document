# 数据权限

数据权限表示用户能访问哪些数据，不能访问哪些数据。通过实现com.ruisi.vdop.ser.ruisibi.DataControlInterface 接口来控制数据权限。

通过用户所属组织机构控制权限示例：

```
/**
* 通过实现DataControlInterface 接口实现数据权限控制。
* 此接口在系统每次查询中都会调用，接口返回数据权限过滤的SQL片段。
* @author zys
* @date 2015-2-20
*/
public class DataControlImp implements DataControlInterface {
/**
* @param u 会话中保存的用户信息
* @param tableAlias 此次查询用到的所有表及其别名
* @param master 此次查询中使用的主表的名称
*/
public String process(User u, Map<String, String> tableAlias, String master) {
int lvl = u.getDeptLvl();
if(lvl == 1){
return " and " + tableAlias.get("DEPT") + ".lv3_id = '"+u.getDeptId()+"' " ;
}else if(lvl == 2){
return " and " + tableAlias.get("DEPT") + ".lv2_id = '"+u.getDeptId()+"' " ;
睿思 BI-OLAP 多维分析工具用户使用手册 北京睿思科技有限公司(www.ruisitech.com)
}else if(lvl == 3){
return " and " + tableAlias.get("DEPT") + ".dept_id = '"+u.getDeptId()+"' " ;
}
return "";
}
}
```

然后在 ext-config.xml 中添加配置：

```
<constant name="dataControl" value="com.ruisi.vdop.ser.ruisibi.DataControlImp"/>
```



