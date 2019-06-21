#### 1.1 基本概念

##### 测试的定义

评测，度量。(from IEEE)

##### 特征

1. 范围：广义的测试从需求开始
2. 内容：静态活动加动态活动
3. 作用：预防失效
4. 意义：尽早发现问题，降低成本
5. 方法：尽量可重用

##### 目的

发现错误，证明程序有错。(from Glenford J. Myers)

测试不负责证明程序无错误，那是形式化证明的事。

好的测试用例是能发现至今未发现的错误。

对软件进行度量和评估，提高软件质量。(from Bill Hetzelt)

##### 原则问题

1. 证伪而非证真
2. 尽早地、不断地测试
3. 重视无效数据和非预期使用习惯的测试
4. 程序员应避免检查自己的程序
5. 注意群集现象(80%的错误集中在20%的模块中)
6. 用例要定期评审
7. 应对每一个测试结果做全面检查
8. 测试现场保护和资料归档
9. 经济性原则

##### 质量保证

- 定义
- 与软件测试的关系

#### 1.2 分类

##### 是否知道源代码

黑盒与白盒，黑盒测试包括功能与性能两种测试

功能测试：逻辑功能、界面、易用性、安装、兼容性

性能测试：一般性能、稳定性、负载、压力

##### 是否运行

- 静态测试：代码、界面、文档
- 动态测试：结构和正确性测试

##### 按开发阶段分

- 单元测试(模块测试)：对软件开发中的最小单位：程序模块进行测试。
- 集成测试(组装测试)：重点测试不同模块的接口部分
- 系统测试：功能测试、性能测试、兼容性测试
- 验收测试：α测试(内测)，β测试(公测)，最终验收测试

##### 其它分类方式

- 回归测试：软件被修改后重新进行的测试，保证软件被修改后没有引入新的错误。
- 冒烟测试：大规模测试前先验证软件的基本功能是否实现，以判断对象是否具备可测试性。
- 随机测试：所有输入数据都是随机生成的，用以模拟用户真实操作。

#### 1.3 缺陷管理

##### 定义

末达到功能、实现了不能有的功能、功能超范围、末达到性能要求、软件难以理解和使用

##### 目标

确保每个被发现的缺陷都能被有效的解决。

##### 内容

严重程序：严重缺陷、较大缺陷、较小缺陷、轻微缺陷、其它缺陷

优先级：立即解决、高优先级、正常排队、低优先级

状态：提交、打开、已拒绝、已解决、已关闭、重新打开

测试环境、描述信息、重现步骤等

##### 生命周期

```flow
st=>start: 打开缺陷(提交)
disp=>operation: 指派缺陷
conf=>condition: 确认缺陷
delay=>condition: 推迟处理
fixed=>operation: 固定
op=>operation: 处理缺陷
regression=>condition: 回归缺陷
e=>end: 关闭缺陷

st->disp->conf
conf(yes)->delay
conf(no)->regression
delay(yes)->fixed
delay(no)->op
fixed->op
op->regression
regression(yes)->e
regression(no)->disp

```

##### 管理工具

bugzilla, bugfree

#### 1.4 软件质量特性与测试特性

##### 软件质量特性

- 静态质量特性：代码与文档
- 动态质量特性：正确性、可靠性、易用性、完整性、一致性、性能

##### 软件测试特性

- 复杂性、经济性

#### 1.5 软件测试充分性及其停止标准

##### 软件测试充分性

定义：T满足C。(测试集T，软件P，软件的需求R，准则C)

覆盖域：从测试准则C中得出的有限集，称为覆盖域Ce。

如Ce仅依赖于代码，则为白盒测试充分性准则；如Ce仅依赖于需求，则为黑盒测试充分性准则。

覆盖率：k/n。(n：覆盖域Ce中的元素数；k：测试集T覆盖了Ce中的元素个数)

如覆盖率为100%，则T对于C是充分的。

##### 停止标准

- 基于测试阶段的原则
- 基于测试用例的原则
- 基于缺陷收敛趋势和缺陷修复率原则
- 基于验收测试的原则
- 基于覆盖率的原则
- 软件项目暂停或终止