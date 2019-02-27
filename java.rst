想星代码规范
=============
第一章:项目结构
----------------
- 1.1 **项目类型**
    想星项目是使用java语言,采用maven构建的微服务的项目。项目父POM工程为Venus,其余子模块项目都为Venus的子模块。
- 1.2 **项目命名**
    项目命名规范:venus-${modulename}(使用中划线分割,所有字母使用小写)。
- 1.3 **包结构**
   |  包的命名规范:所有包都必须是com.xiangxing.venus.${modulename}开头，包名都有小写单词组成;
   |  包的路径符合所开发的系统模块的定义，比如框架对框架，商品对商品，基础类对基础类。
   |  以便看了包名就明白是哪个模块，从而直接到对应包里找相应的实现。
- 1.4 **资源文件**
   |  项目的资源文件都必须在resources目录下面,基本配置文件采用yml的文件格式。
   |  如果是项目框架的配置一定要新建框架相关名称文件夹,便于方式识别和管理。

第二章:接口规范
----------------
- 2.1 **返回值类型**
   |  除了ADMIN和APP项目外,其他微服务项目的接口返回值都使用同一的类,
   |  m.xiangxing.venus.base.framework.dto.BaseRespDto<T>；
   |  泛型T必须为具体对象不能使用基本数据结构和map类型。所有业务异常必须有统一的@ExceptionHandler方法处理。
- 2.2 **入参类型**
   *  GET: 简单参数,使用路径变量或者查询参数
   *  POST:复杂参数,必须使用对象
   *  PUT:同POST
   *  DELETE:同GET

第三章:注释
----------------
- 1.1 **swagger规范**
- 1.1.1 **使用@ApiOperation每一个url资源的说明**
        @ApiOperation(value = “获取用户列表”,notes = “根据url的id来获取用户详细信息，返回List类型的JSON用户信息”)
- 1.1.2  **使用@ApiImplicitParam对容器(参数)的描述**
        @ApiImplicitParam(name = “user”, value = “用户详细实体user”, required = true, dataType = “User”)
- 1.1.3  **使用@ApiModelProperty对model中某字段属性的描述**
        @ApiModelProperty(value = “id”,required = true)
- 1.1.4  **model描述**
   |  @ApiModelProperty(value = “用户姓名”,required = true)
   |  private String name; 
   |  对字段的描述
- 2.1 **类注释和方法注释**
    在Github上有模板

第四章:代码
---------------
- 1.1 **基本规范**
   *  实体类使用lomok,可以省略使用GET,SET方法
   *  每个controller和service入口需要加log日志
   *  待补充
   *  [参考阿里巴巴java代码规范] `代码规范 <https://files-cdn.cnblogs.com/files/han-1034683568/%E9%98%BF%E9%87%8C%E5%B7%B4%E5%B7%B4Java%E5%BC%80%E5%8F%91%E6%89%8B%E5%86%8C%E7%BB%88%E6%9E%81%E7%89%88v1.3.0.pdf>`_







