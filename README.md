# My_Test_Project
my_test_project demo
基于excel的接口自动化测试框架

git仓地址：https://github.com/zhouqingtao2006/test_project

<h2>框架结构说明</h2>

整个测试框架分为四层，通过分层的方式，测试代码更容易理解，维护起来较为方便。

**第一层是“测试工具层”：**

* util 包：用于实现测试过程中调用的工具类方法，例如读取配置文件、接口请求方法、生成测试报告、发送邮件等。
* conf 目录：存放配置文件。
* log 目录：日志输出文件。

**第二层是“服务层”：相当于对测试对象的一个业务封装。对于接口测试，是对远程方法的一个实现；对于 UI 测试，是对页面元素或操作的一个封装。**

* action 包：实现了对一个接口的请求，包含请求数据的参数化预处理及响应数据的关联提取。

**第三层是“测试用例逻辑层”：该层主要是将服务层封装好的各个业务对象，组织成测试逻辑，进行校验。**

* bussiness_process 包：基于关键字的形式，实现具体模块或测试用例集的测试脚本逻辑。
* test_data 目录：Excel 测试数据文件，包含请求地址、请求方法、请求数据、关联关键字等。

**第四层是“测试场景层”：将测试用例组织成测试场景，实现各种级别 cases 的管理，如冒烟，回归等测试场景。**

* main.py：本框架工程的运行主入口。
