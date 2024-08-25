# 数据库系统原理

## 第一章：数据库系统概述

### 数据库基本概念

- 数据

	- 数据是描述事物的符号记录，是指用物理符号记录下来的，可以鉴别的信息。

可以是文本数据，也可以是多媒体数据

- 数据库

	- 存储数据的仓库。是长期存储在计算机中的有组织，可共享的数据集合。

一般数据库结构清晰，数据独立，冗余度较小，利于扩展。

- 数据库管理系统

	- 定义

		- 用于建立和管理数据的软件，介于应用程序与操作系统之间

	- 功能

		- 数据定义

			- 提供 DDL 语言用于定义数据库中的数据表，对象，视图等

		- 数据操纵

			- 提供 DML 语言用于对数据进行增删改查

		- 数据组织，存储，管理

		- 数据库的建立和维护

			- 备份和恢复，性能监测等

		- 数据库的运行管理

			- 提供统一管理机制，保证并发性，安全性，可靠性。

		- 其他功能

			- 与其他软件的通信功能

- 数据库管理员

	- 负责对数据进行维护，确保数据库高效运行

- 用户

	- 数据系统的服务对象，包括程序员和数据库终端用户

- 数据库系统

	- 数据库系统是指在计算机中引入数据库技术之后的系统，一个完整的数据库系统应包含：数据库软件，数据库管理系统，数据库管理员，用户，应用软件，相关实用工具。

### 数据库管理技术的发展

- 数据管理的任务

	- 数据的收集，组织，控制，存储，选取，维护

- 三个阶段

	- 人工管理阶段（50 年代中期 - 之前）

		- 数据不保存

		- 应用程序管理数据

		- 数据面向应用，冗余性大

	- 文件系统阶段（50 年代后期 - 60 年代中期）

		- 数据可以长期保存和专门管理

		- 具有物理数据独立性，数据的物理存储结构与应用程序的逻辑结构相分离

		- 数据只能实现文件级的共享，冗余性大

	- 数据库系统阶段（60 年代后期 - 现在）

		- 数据集成

		- 数据独立性高

		- 数据共享性高

		- 数据冗余性小

		- 数据一致性

		- 数据逻辑结构与物理结构相互独立

		- 实现统一管理与控制

			- 数据的安全性

			- 完整性

			- 并发控制

			- 故障恢复

		- 减少应用程序开发与维护的工作量

### 数据库系统的结构

- 视角

	- 数据库管理员

		- 内部系统结构

			- 三级模式结构

				- 外模式（子模式、用户模式）

					- 是数据库用户能看见和使用的局部数据的逻辑结构和特征描述，外模式可以有多个

				- 模式（概念模式、逻辑模式）

					- 是数据库中全体数据的逻辑结构和特征描述，是所有用户的公共数据视图。

既不涉及数据的物理存储细节和硬件环境，也与具体的应用程序，程序设计语言无关，一个数据库只有一个模式。

				- 内模式（存储模式）

					- 是对数据库中数据的物理结构和存储方式的描述，是数据在数据库内部的表示形式，内模式只能有一个

		- 外部体系结构

			- 集中式

			- 分布式

			- 并行式

	- 用户

		- 客户/服务器结构

		- 浏览器/服务器结构

- 映像

	- 定义

		- 映像是一种对应规则，指出映像双方是如何进行转换的

	- 外模式/模式映像

		- 定义了外模式和模式的映像关系，在各自模式中加以描述。

数据库系统的模式如若发生改变，数据库管理员（DBA）通常会对各个外模式/模式的映像做出相应的改变，以使那些对用户可见的外模式保持不变，从而应用程序的编程人员就不必去修改那些依据数据的外模式所编写的应用程序，如此实现了外模式不受模式变化的影响，并保证了数据与程序的逻辑独立性。

	- 模式/内模式映像

		- 定义了数据库全局逻辑结构与物理存储之间的对应关系，通常在模式中加以描述。

保证了数据的物理独立性

- 运行与应用结构

	- BS

	- CS

### 数据模型

- 定义

	- 是模型化数据和信息的工具，也是数据库系统的核心和基础

- 模型

	- 定义

		- 模型是现实世界特征的模拟和抽象表达，有助于理解客观世界中的事物，对象。

	- 三层模型

		- 概念层数据模型

			- 定义

				- 描述现实世界的事物，与计算机系统无关，独立于任何 DBMS

			- 相关概念

				- 实体

					- 客观存在且可以相互区别的事物

				- 属性

					- 实体所具有的某种特性

				- 码或键

					- 唯一标识实体

				- 域

					- 属性的取值范围

				- 实体型

					- 实体名与属性名集合的抽象

				- 实体集

					- 同型实体的集合

				- 联系

					- 现实世界中事物内部与事物之间的联系在信息世界中反映为实体内部与实体之间的联系

		- 逻辑层数据模型

			- 定义

				- 是用户通过数据库管理系统看到的现实世界，是基于计算机的视角对数据进行建模和表示

			- 主要的逻辑模型

				- 层次模型（最早）

					- 有向树（组织结构）

				- 网状模型

					- 网状结构

				- 关系模型

					- 二维表结构

						- 优点

							- 建立在严格的数学概念基础上

							- 数据结构简单，清晰，易用

							- 具有更高的数据独立性，更好的安全保密性，简化了开发工作

				- 面向对象模型

					- 面向对象方法与数据库结合所构成的数据模型

		- 物理层数据模型

			- 描述数据在存储介质上的组织结构，是逻辑层数据模型的物理实现

- 三要素

	- 数据结构

		- 系统的静态属性

	- 数据操作

		- 系统的动态属性

	- 数据约束

		- 数据的相互制约，以保证数据的正确性，有效性，相容性

### ER 图

- 实体用矩形，属性用椭圆形，联系用菱形

- 一对一联系

	- 例如班长和班级的关系

- 一对多联系

	- 例如班级和学生的关系

- 多对多联系

	- 例如课程与学生的关系

## 第二章：关系数据库

### 概述

- 关系数据库是目前应用最广泛的数据库，它以关系模型作为数据的逻辑模型，采用关系作为数据的组织方式，数据库操作建立在关系代数的基础上，具有坚实的数学基础。关系数据库具有较高的数据独立性，当存储结构发生变化时，不会影响应用程序，可以减少维护的工作量

### 发展

- 1970 年

	- 美国 IBM 的 E.F.Codd 提出，开启新纪元

- 70 年代末

	- 关系方法的研究和软件研制取得重大突破

- 80 年代后

	- 逐渐取代网状模型，成为主流数据模型

### 常见的关系型数据库

- Oracle, Sybase, Informix, Foxpro, IBM DB2, MySQL...

### 关系数据模型

- 概念

	- 关系模型只包含单一的数据结构：关系

实体（间）的联系通过关系表示

在用户看来，关系模型是把数据库表示为关系的集合，以二维表格的形式组织数据

- 组成元素

	- 数据结构

	- 操作集合

	- 完整性约束

- 基本术语

	- 表（Table）/ 关系

		- 由唯一的表名，若干列和行数据组成

			- 三种关系类型

				- 基本关系/基本表

					- 实际存在的表

				- 查询表

					- 查询结果对应的表

				- 视图表

					- 由基表或其他视图表导出的表，是虚表

	- 列（Column）/字段/属性

		- 表中每一列有一个名称，称为列名，每一列表示实体的一个属性，具有相同的数据类型

	- 元或度

		- 表中属性的个数

	- 属性值

		- 列的值

	- 行/元组（Tuple）/记录

		- 表中的行

	- 分量

		- 元组中的一个属性值

	- 码或键

		- 够唯一标识关系中每一元组的属性（或属性组合）

	- 超码/超键

		- 一个码，去掉某个属性后仍然是码，这样的码就是超码

最大的超码：所有属性的集合

	- 候选码/候选键（Candidate Key）

		- 一个或一组属性，这组属性可以唯一标识表中的每一行，并且没有冗余的属性。一个表可以有一个或多个候选码。

候选码就是最小的超码

	- 主码/主键（Primary Key）

		- 在候选码中选出一个作为主要的标识符。每个表只能有一个主码，用来唯一确定每一条记录。

	- 外码/外键

		- 一个表中的属性，它是另一个表的主键。外码用于关联两个表。

	- 全码/全键

		- 一个表中的所有属性的组合，当这个组合可以唯一标识表中的每一行时，称为全码。

	- 主属性

		- 包含在任何候选键中的属性

	- 参照关系（从关系）

		- 含有外键的表，这个外键指向另一表的主键。

	- 域（Domain）

		- 数据库表中某一列（或属性）可取的值的集合。域定义了属性可能的值的类型和限制

	- 数据类型（Data Type）

		- 属性值的类型，如整数、浮点数、字符串等。

	- 关系模式（Relation Schema）

		- 定义了关系的结构，包括关系的名称、属性和各属性的数据类型等

	- 关系数据库（Relational Database）

		- 使用关系模型来组织数据的数据库，数据以表格形式存储，表格中的数据项之间可通过键的关系相互关联

- 关系数据库对数据的限定

	- 每一个关系仅有一种关系模式

	- 每一个关系模式中的属性必须命名且不同

	- 每一个属性都是不可分解的

	- 同一个关系中不允许出现同一个候选码值完全相同的元祖

- 基本的关系操作

	- 操作方式

		- 查询

			- 选择（σ）

				- σ age > 30(Employees) 从 Employees 表中选择所有年龄大于 30 的员工。

			- 投影（π）

				- π name, age(Employees) 从 Employees 表中选择 name 和 age 列。

			- 并（∪）

				- Employees ∪ Managers 包含在 Employees 和 Managers 表中的所有元组。

			- 差（−）

				- Employees − Managers 包含在 Employees 表中但不在 Managers 表中的元组

			- 笛卡尔积（×）

				- Employees × Departments 将 Employees 表中的每个元组与 Departments 表中的每个元组合并

			- 交（∩）

				- Employees ∩ Managers 包含在 Employees 和 Managers 表中的共同元组

			- 连接（⨝）

				- Employees ⨝ Departments 连接 Employees 表和 Departments 表，通常根据共同的属性（例如部门 ID）进行连接

		- 插入

		- 删除

		- 修改

	- 三大要素

		- 操作对象

		- 操作符

		- 操作结果

	- 集合运算

		- 二目运算

			- 并（∪）

				- 并操作用于合并两个表的行，并消除重复的行。这两个表必须具有相同的属性和数据类型。

				- S1∪S2 会合并这两个表中的学生记录，重复的记录只保留一条。

			- 交（∩）

				- 找出同时在两个关系中出现的元组。

			- 差（−）

				- 差操作用于从第一个表中去除所有存在于第二个表中的行。这两个表同样必须具有相同的属性和数据类型。

				- S1 − S2 会从 S1 中删除所有在 S2 中也出现的记录。

			- 笛卡尔积（×）

				- 笛卡尔积操作用于两个表的每一行与另一个表的每一行组合，生成所有可能的行对组合。如果两个表分别有 m 和 n 行，结果将有 m×n 行。

				- 学生表 × 课程表 将为每个学生与每门课程创建一个组合，如果学生表有100个学生，课程表有10门课，则结果将有1000行。

	- 关系运算

		- 一元专门关系操作

			- 一元专门关系操作只涉及单个关系（即单个数据表），例如：选择和投影

				- 选择 SELECT（σF(R)）

				- 投影 PROJECTION（πA(R)）

					- 投影出的表不含重复元组

		- 二元专门关系操作

			- 二元专门关系操作涉及两个关系，例如：并，差，交，笛卡尔积

				- 连接 JOIN（θ）

					- 等值连接

						- 通过两个表之间特定的列，应用相等的条件来结合它们的行

					- 自然连接

						- 自动使用两个表中的相同的列名作为连接条件，会自动省略重复的列

	- 关系的完整性约束

		- 实体完整性的约束

			- 关系中的主码不能为空

		- 参照完整性的约束

			- 属性（或属性组）F 是基本关系 R 的外码，
它与基本关系 S 的主码 K 相对应，则对于 R 中每个元组在 F 上的值只允许两种可能，要么取空值，要么等于 S 中某个元组的主码值

		- 用户定义完整性约束

			- 是根据具体应用需求定义的额外约束，它
反映了某一具体应用所涉及的数据应满足的要求。关系模型提供定义和检验这类完整性规则的机制，其目的是用统一的方式由系统来处理它们，不再由应用程序来完成这项工作。

		- 检验

			- 执行插入操作

				- 先检查实体完整性，再检查参照完整性，最后检查用户定义完整性

			- 执行删除操作

				- 拒绝删除

				- 空值删除

				- 级联删除

			- 执行更新操作

				- 上述两种情况的综合

### 规范化理论

- 是一套用于设计关系数据库结构的方法和准则，旨在减少数据冗余和提高数据一致性。
规范化理论通过将数据库划分成多个表，并定义表之间的关系，来确保数据的逻辑性和完整性

- 关系模式中可能存在的冗余和异常问题

	- 数据冗余

	- 更新异常

	- 插入异常

	- 删除异常

- 函数依赖

	- 定义

		- 给定关系 R 和属性 X、Y，如果对于 R 中的每个可能的元组，属性集 X 的值唯一确定属性集 Y 的值，则称 X 决定 Y：X→Y

反之，如果 X 不能决定 Y，则记为：X ⍆ Y

	- 完全函数依赖

		- 如果属性集 Y 对属性集 X 完全函数依赖，并且 Y 不依赖于 X 的任何真子集，则称 Y 完全函数依赖于 X

		- 例如：在关系 R{A, B, C} 中，如果 {A, B} → C 并且 C 不依赖于 A 和 B 单独存在，那么 C 完全函数依赖于 {A, B}

{StudentID, CourseID} → Grade 表示 Grade 完全依赖于 (StudentID, CourseID)

	- 部分函数依赖

		- 如果属性集 Y 对属性集 X 函数依赖，但 Y 依赖于 X 的一个真子集，则称 Y 部分函数依赖 X。

		- 例子：{StudentID, CourseID} → StudentName 表示 StudentName 部分依赖于 (StudentID, CourseID)，因为 StudentName 实际上只依赖于 StudentID。

	- 传递函数依赖

		- 如果 X → Y 且 Y → Z，则 X → Z 为传递函数依赖

		- 例子：假设 EmployeeID → DepartmentID 且 DepartmentID → DepartmentName，则存在传递依赖 EmployeeID → DepartmentName。

- 候选关键字

	- 用来唯一标识表中元组的一种属性，一个表可以有多个候选关键字，每个候选关键字都能够唯一标识一条记录

	- 候选关键字的条件

		- 唯一性

			- 在表中，每个候选关键字的组合值必须唯一。这意味着没有两个不同的记录在候选关键字的所有属性上有相同的值

		- 最小性

			- 候选关键字的属性集合是最小的，这意味着如果去掉其中任何一个属性，剩下的属性集合就不再具有唯一性

- 范式与规范化过程

	- 定义

		- 教科书：
一个低一级范式的关系模式通过模式分解可以转换成若干个高一级范式的关系模式的集合。
所有的关系结构都必须是规范化的，即至少是第一范式

	- 第一范式

		- 第一范式要求表中的每个列都具有原子性，即每一列都是不可再分的

		- 存在的问题

			- 数据冗余

			- 插入异常

			- 删除异常

	- 第二范式

		- 满足第一范式

		- 每个非主属性完全依赖于主键，消除非主属性对候选关键字的部分函数依赖

	- 第三范式

		- 满足第二范式

		- 消除非主属性之间的传递函数依赖（每个非主属性直接依赖于主键）

	- BCNF 范式

		- 每一函数依赖的决定因素都包含一个候选关键字

## 第三章：数据库设计

### 数据库设计概述

- 数据库的生命周期

	- 数据库分析与设计阶段

		- 需求分析

		- 概念设计

		- 逻辑设计

		- 物理设计

	- 数据库实现与操作阶段

		- 数据库的实现

		- 操作与监督

		- 修改与调整

- 数据库设计的目标

	- 满足应用功能需求

		- 主要是指用户当前与可预知的将来应用所需要的数据及其联系， 应全部准确地存储在数据库之中， 从而可满足用户应用中所需要的对数据进行的存、取、 删、 改等操作

	- 良好的数据库性能

		- 主要是指对数据的高效率存取和空间的节省， 并具有良好的数据共享性、完整性、一致性及安全保密性。

- 数据库设计的内容

	- 数据库设计是从用户对数据的需求出发，研究并
构造数据库的过程

	- 数据库结构设计

	- 数据库行为设计

		- 确定数据库用户的动态行为和动作

- 数据库设计的过程

	- 需求分析阶段

	- 结构设计阶段，其包括概念结构设计、 逻
辑结构设计和物理结构设计

	- 行为设计阶段，其包括功能设计、事务设计
和程序设计

	- 数据库实施阶段，其包括加载数据库数据和
调试运行应用程序

	- 数据库运行和维护阶段

- 数据库设计的方法

	- 规范设计法

		- 新奥尔良(New Orleans)设计方法

			- 1978 年提出，目前公认的较为完整和权威的一种规范设计方法

			- 内容

				- 需求分析

				- 概念结构设计

				- 逻辑结构设计

				- 物理结构设计

			- 缺点：不太考虑数据库的行为设计

		- 基于E-R模型的数据库设计方法

			- 由 P.P.S.Chen 于 1976 年提出的，其基本思想是在需求分析的基础上用 E-R 图构造一个反映现实世界实体之间联系的企业模式，然后将此模式转换成某一特定 DBMS 下的概念模式。

		- 基于第三范式的设计方法

			- 一类结构化设计方法，其思想是在需求分析的基础上首先确定数据库的模式、属性及属性间的依赖关系，然后将它们组织在一个单一的关系模式中，再分析模式中不符合第三范式的约束条件，进行模式分解， 规范成若干个第三范式关系模式的集合。

	- 直观设计法

		- 利用设计者的经验和技巧来设计数据库模式

		- 缺点：缺乏科学理论的指导， 设计的质量很难保证

	- 计算机辅助设计法

		- 在数据库设计过程中，以领域专家的知识或经验为主导， 模拟某一规范化设计的方法，通常通过人机交互的方式来完成设计的某些过程

### 数据库设计的基本步骤

- 分阶段规范设计方法遵循自顶向下、逐步求精的原则，将数据库设计过程分解为若干个相互依存的阶段。

- 需求分析

	- 需求分析的目标是了解与分析用户的信息及应用 处理的要求,并将结果按一定格式整理而形成需求分析报告

	- 该分析报告是后续概念设计、逻辑设计、物理设计、数据库建立与维护的依据

	- 需求分析的基本方法是听取数据库应用部门工作人员的报告，并与之座谈。 同时，需求分析人员可提交一份需求调查表

	- 步骤

		- 确定数据库范围

			- 确定数据库应支持哪些应用功能

		- 分析数据应用过程

			- 指了解并分析数据与数据处理间的关系

是数据库应用程序编写的依据

		- 收集与分析数据

			- 任务是了解并分析数据的组成格式及操作特征，每个数据元素的语义及关系等，并将它们收集起来整理归档

			- 三方面

				- 静态结构

					- 通过数据分类表和数据元素表进行说明

				- 动态结构

					- 可通过任务分类表和数据操作特征表进行说明

				- 数据约束

					- 数据安全保密性

						- 是指针对各种不同类数据，谁拥有操作（存、 取、删、改）的不同授权

					- 数据完整性

						- 是指数据正确性的约束范围和验证准则，以及一致性保护的要求

					- 响应时间

						- 是指某些特定应用要求的数据存取的时间限制

					- 数据恢复

						- 是指转储及恢复的时机与范围等要求

		- 编写需求分析报告

			- 作为需求分析阶段的一个总结， 数据库设计人员需要编写需求分析报告

			- 主要内容

				- 数据库的应用功能目标

				- 标明不同用户视图范围

				- 应用处理过程需求说明

				- 数据字典

					- 各类数据详细描述的集合

它提供了对各类数据描述的集中管理，是一种数据分析、系统设计和管理的有力工具

				- 数据量

				- 数据约束

- 概念结构设计

	- 在需求分析中产生的需求分析报告的基础上，按照特定的方法设计满足应用需求的用户信息结构，该信息结构通常称为概念模型

	- 常用方法

		- 实体分析法（自顶向下）

		- 属性综合法（自底向上）

- 逻辑结构设计

	- 将概念模型转换为等价的、并为特定 DBMS 所支持数据模型的结构

	- 步骤

		- 模型转换

			- 模型转换是指将概念模型等价地转换为特定 DBMS 支持的关系模型、网状模型或层次模型表示

		- 子模式设计

			- 抽取或导出模式的子集，以构造不同用户使用的局部数据逻辑结构

		- 编制应用程序设计说明

			- 是为可实际运行的应用程序设计提供依据与指导，并作为设计评价的基础

		- 设计评价

			- 分析并检验模式及子模式的正确性
与合理性

- 物理设计

	- 是指对于一个给定的数据库逻辑结构，研究并构造物理结构的过程

	- 主要任务

		- 确定数据库在存储设备上的存储结构及存取方法

		- 因 DBMS 的不同还可能包括建立索引和聚集

		- 物理块大小、缓冲区个数和大小、数据压缩的选
择等

- 数据库实施

	- 加载数据

	- 应用程序设计

	- 数据库试运行

- 数据库运行和维护

	- 数据库系统投入实际运行标志着数据库设计和应用开发的基本完成，但绝不意味着设计和应用开发工作的终止。

	- 系统维护中最困难的工作是数据库重组与重构

### 关系数据库设计方法

- 概念结构设计方法

	- 通常采用自顶向下法

		- 建立局部信息结构

			- 步骤

				- 确定局部范围

				- 选择实体

				- 选择实体的关键字属性

				- 确定实体间联系

				- 确定实体的属性

		- 然后将局部信息结构合成为全局信息结构并优化，其中使用 E-R 图作为概念模型的描述工具

			- 要达到的目的

				- 实体类型个数尽可能少

				- 实体类型所含属性尽可能少

				- 实体类型间联系无冗余

			- 各局部 E-R 图冲突表现

				- 属性冲突

				- 命名冲突

				- 结构冲突

- 逻辑结构设计方法

	- 任务是把在概念结构设计产生的概念模型转换为具体的 DBMS 所支持的逻辑数据模型，也就是导出特定的 DBMS 可以处理的数据库逻辑结构（数据库的模式和外模式）

	- 包括

		- 将 E-R 图转换为关系模型

			- 要解决的问题

				- 如何将实体以及实体间的联系转换为关系模式

				- 如何确定这些关系模式的属性和主码

			- 转换原则

				- 一个实体型转换为一个关系模式

				- 一对一联系可以与任意一端对应的关系模式合并

				- 一对多联系可以与 N 端对应的关系模式合并

				- 多对多联系可以转换为一个关系模式

				- 三个或三个以上实体间的一个多元联系可以转换为一个关系模式

		- 对关系数据模型进行优化

			- 数据库逻辑设计的结果不是唯一的。为了进一步
提高数据库应用系统的性能，还应该根据应用需
要适当地修改、调整数据模型的结构

			- 方法

				- 确定各属性间的函数依赖关系

				- 对于各个关系模式之间的数据依赖进行极小
化处理，消除冗余的联系

				- 判断每个关系模式的范式，根据实际需要确
定最合适的范式

				- 按照需求分析阶段得到的处理要求，分析这些模式对于这样的应用环境是否合适，确定是否要对某些模式进行合并或分解

				- 对关系模式进行必要的分解，提高数据操作
的效率和存储空间的利用率

		- 设计面向用户的外模式

			- 将概念模型转换为全局逻辑模型之后，可根据局部应用需求，利用视图设计更符合局部用户需要的用户外模式

			- 考虑的问题

				- 可以通过视图机制在设计用户视图时，重新定义某些属性的别名，使其更符合用户的习惯，以方便使用

				- 可以对不同级别的用户定义不同的视图，以
保证系统的安全性

				- 简化用户对系统的使用

- 物理设计方法

	- 物理设计的任务主要是通过对关系建立索引和聚集来实现与应用相关数据的逻辑连接和物理聚集，以改善对数据库的存取效率。

		- 建立索引

			- 索引的建立是通过 DBMS 提供的有关命令来实现

			- 建立索引的方式通常有静态和动态两种

		- 建立聚集

			- 聚集是将相关数据集中存放的物理存储技术，借以提高 I/O 的数据命中率而改善存取速度，其功能由具体的 DBMS 所提供

			- 数据聚集结构的一种有效方式是块结构方式，块与块之间由指针链接，一个块对应一个物理分区

## 第四章：SQL 与关系数据库基本操作

### SQL 概述

- SQL 已经成为关系数据库的标准语言，它的功能包括数据查询、数据定义、数据操纵、数据控制等与数据库系统有关的功能

- 发展

	- 1974 年 Boyce 和 Chamberlin 提出

		- 称为数据库时代

	- 1986 年 10 月：最早的 SQL 标准

	- 1987 年 6 月：成为国际标准

	- 1989 年 4 月：ISO 提出 SQL-89

	- 1992 年，ANSI 和 ISO 共同颁布 SQL-92(SQL 2)

	- 1999 年，颁布 SQL-99(SQL 3)

- 目前没有一个数据库系统能够支持 SQL 标准的全部概念和特性

- SQL 语句不区分大小写

- 核心部分：

	- 数据定义语言（DDL）

		- 主要用于数据库对象的创建、删除、修改等操作

			- 对象主要包括：

				- 表

				- 默认约束

				- 规则

				- 视图

				- 触发器

				- 存储过程

		- 主要 SQL 语句：

			- CREATE

			- ALTER

			- DROP

	- 数据操纵语言（DML）

		- 主要用于操纵数据库中各种对象，特别是检索和修改数据

		- 主要 SQL 语句

			- SELECT

			- INSERT

			- UPDATE

			- DELETE

	- 数据控制语言（DCL）

		- 主要用于安全管理，例如确定用户的数据库权限

		- 主要 SQL 语句

			- GRANT

			- REVOKE

	- 嵌入式和动态 SQL 规则

	- SQL 调用和会话规则

		- SQL 调用

			- 包括 SQL 例程和调用规则，以便提高 SQL 的灵活性、有效性、共享性以及使 SQL 具有更多高级语言的特征

### SQL 预备知识

- MySQL 是一个关系数据库管理系统，具有客户/服务器体系结构，最初由瑞典 MySQL AB 公司开发

- MySQL 具有体积小、速度快、开放源代码、遵循 GPL 等特点，许多中小型网站为了降低网站总体拥有成本而选择它。

- 两种架构方式

	- LAMP

		- Linux + Apache + MySQL + PHP/Perl/Python

	- WAMP

		- Windows + Apache + MySQL + PHP/Perl/Python

- MySQL 中的 SQL

	- 基本表是独立存在的表，一个关系对应一个基本表，一个或多个基本表对应一个存储文件，一个表可以有若干索引，索引也存放在存储文件中，存储文件的逻辑结构组成了 MySQL 的内模式，并且存储文件的物理结构对最终用户是隐蔽的

	- 视图是一个虚表，是从一个或几个基本表导出的表，数据库只存储视图的定义而不存储视图对应的数据

	- MySQL 在 SQL 的基础上增加了部分扩展的语言要素

		- 常量

			- 在程序运行过程中值不变的量，也成为字面量或标量值

			- 可分为

				- 字符串常量

					- 用引号括起来的字符，分为 ASCII 字符串常量和 Unicode 字符串常量

				- 数值常量

					- 分为整数常量和浮点数常量

				- 十六进制常量

					- 通常指定为一个字符串变量，比如：X41/x41/0x41

				- 日期时间常量

					- '2020-06-19'

				- 位字段值

					- 使用 b'value' 格式书写，例如：b'01001'

				- 布尔值

					- TRUE(1)/FALSE(0)

				- NULL 值

		- 变量

			- 用于临时存储数据，变量中的数据可以随着程序变化

			- 属性

				- 名字

				- 数据类型

			- 两种变量

				- 用户变量

					- @myVar

				- 系统变量

					- @@mySysVar

					- 全局系统变量

						- -- 设置全局系统变量
SET @@global.max_connections = 1000;

					- 用户系统变量

						- -- 设置会话系统变量
SET @@session.sort_buffer_size = 256000;

		- 运算符

			- 算数运算符

				- +-*/%

			- 位运算符

				- &|^~>><<

			- 比较运算符

				- =

				- >

				- <

				- >=

				- <>/!=

					- 不等于

				- <=>

					- 相等或都等于空

			- 逻辑运算符

				- NOT/!

					- 逻辑非

				- AND/&&

					- 逻辑与

				- OR/||

					- 逻辑或

				- XOR/^

					- 逻辑异或（一个为 TRUE，一个为 FALSE 时相等）

		- 表达式

			- 是常量，变量，列名，复杂计算，运算符和函数的组合

			- 根据表达式的值的数据类型，分为

				- 字符型表达式

				- 数值型表达式

				- 日期表达式

		- 内置函数

			- 数学函数

				- ABS()

				- SQRT()

			- 聚合函数

				- COUNT()

				- AVG()

			- 字符串函数

				- ASCII()

				- CHAR()

			- 日期和时间函数

				- NOW()

				- YEAR()

			- 加密函数

				- ENCODE()

				- ENCRYPT()

			- 控制流程函数

				- IF()

				- IFNULL()

			- 格式化函数

				- FORMAT()

			- 类型转换函数

				- CAST()

			- 系统信息函数

				- USER()

				- VERSION()

### 数据定义

- 数据库模式定义

	- 数据库的创建

		- CREATE {DATABASE|SCHEMA} [IF NOT EXISTS] db_name;

	- 选择

		- USE db_name;

	- 修改

		- ALTER DATABASE mysql_test DEFAULT CHARACTER SET gb2312 DEFAULT COLLATE gb2312_chinese_ci;

	- 删除

		- DROP {DATABASE|SCHEMA} [IF EXISTS] db_name;

	- 查看

		- SHOW {DATABASES|SCHEMA} [LIKE ‘pattern’|WHERE expr];

	- IF EXISTS

		- 可以避免操作时不存在而报错

- 表定义

	- 数据表是关系数据库中最基本、最重要的数据对象

	- 数据表被定义为字段的集合

	- 临时表

		- 在创建表的时候，如果添加 TEMPORARY 关键字，则表示创建临时表，临时表只对创建的人可见，SQL 连接关闭后会自动删除

	- 持久表

	- 数据类型

		- 整型 int

		- 浮点型 double

		- 布尔型 BOOLEAN

			- TINYINT

		- 日期和时间类型

			- 日期 date

			- 时间戳 timestamp

			- 时间型 time

		- 字符串类型

			- 定长字符类型 char

			- 可变长字符类型 varchar

		- 空间数据类型

	- AUTO_INCREMENT

		- 自增，在创建表时，可以为数据类型是整型的列设置该属性，当插入一个 NULL 或者 0 时，该列的值会被自动设置为表中当前列最大值 + 1。自增从 1 开始，每个表只能有一个自增，并且必须被索引

		- 值可以被覆盖，但是需要唯一

	- DEFAULT

		- 默认值

	- NULL

		- 没有值

		- 每个表的列只有 NULL/NOT NULL 两种

		- NULL 值与空字符串不一样

	- PRIMARY KEY

		- 主键，值唯一

		- 主键只能是 NOT NULL

	- ALTER TABLE

		- 更新表结构

		- ADD

			- 添加字段

			- ALTER TABLE table_name
ADD [COLUMN] 字段名 数据类型 [列级完整性约束条件] [默认值] [FIRST | AFTER col_name];

		- CHANGE

			- 用于更改列名和列的数据类型，必须同时指定旧列名和新列名

			- 如果修改字段时，同时修改了字段的数据类型，
如果新的数据类型和旧的不兼容则会报错，如果兼容则可能会丢失部分数据

		- MODIFY

			- 用于更改列的数据类型和属性（不更改列名）。
只需指定列名和新的数据类型及属性。

		- DROP

			- 删除列，也可以删除主键，外键，索引等

		- RENAME

			- 修改表名

	- RENAME TABLE

		- 重命名表

		- RENAME TABLE old_name1 TO new_name1 [, old_name2 to new_name2]

	- DROP TABLE

		- 删除表

		- DROP [TEMPORARY] TABLE [IF EXISTS]

name [,name2];

	- 查看表

		- 查看表的名称

			- SHOW [FULL] TABLES [{FROM|IN} db_name] [LIKE ‘pattern’|WHERE expr];

		- 查看表的结构

			- SHOW [FULL] COLUMNS [{FROM|IN} tbl_name] 
[{FROM|IN} db_name] 
[LIKE ‘pattern’|WHERE expr];

			- 或者

{DESCRIBE|DESC} table_name [column_name|wild]

- 索引定义

	- 索引实质上是一张描述索引列的列值与原表记录行之间一一对应关系的有序表

一个表可以创建多个索引，但是每个索引名都必须是唯一的

	- 弊端

		- 索引是以文件的形式存储，一个表的索引保存在同一个索引文件中，占用磁盘空间

		- 索引会提高查询速度，但是会降低更新速度

	- 索引分类

		- 普通索引

			- 关键字是 INDEX 或 KEY

				- CREATE INDEX index_name ON tbl_name(index_col_name,…); 

其中，index_col_name的格式为： col_name [(length)] [ASC|DESC]

		- 唯一性索引

			- 索引列中的所有值都是唯一的

				- ALTER TABLE mysql_test.seller ADD UNIQUE INDEX index_seller_name(seller_name);

		- 主键

			- 表的唯一主标识索引

	- 查看索引

		- SHOW INDEX FROM table_name;

	- 删除索引

		- DROP INDEX index_name ON table_name

		- ALTER TABLE table_name DROP {PRIMARY KEY| INDEX|FOREIGN KEY} index_name;

- 视图定义

### 数据更新

- INSERT

	- INSERT INTO ... VALUES

		- INSERT INTO Employee (EmpID, EmpName, Salary, DeptID) VALUES
(1, 'Alice', 70000, 1)

	- INSERT INTO ... SET

		- INSERT INTO table_name SET column1 = 'value1', column2 = 'value2', column3 = 'value3';

- UPDATE ... SET

	- UPDATE table_name SET col_name1={expr1|DEFAULT}[,col_name2={expr2|DE
FAULT}] [WHERE where_condition] [ORDER BY …] [LIMIT row_count];

- DELETE FROM tbl_name

	- DELETE FROM table_name [WHERE where_condition] [ORDER BY …] [LIMIT row_count];

### 数据查询

- SELECT

	- SELECT [ALL|DISTINCT|DISTINCTROW] select_expr[,select_expr …]
FROM table_references
[WHERE where_condition]
[GROUP BY {col_name|expr|position} [ASC|DESC],… [WITH ROLLUP]]
[HAVING where_condition]
[ORDER BY {col_name|expr|position} [ASC|DESC],… ]
[LIMIT {[offset,] row_count|row_count OFFSET offset}];

		- select_expr 可以指定以下五种方法

			- 选择指定的列

			- 定义并使用列的别名

			- 替换查询结果集中的数据

				- SELECT cust_name, CASE WHEN sex = ‘M’ THEN ‘男’ ELSE ‘女’ END AS 性别 FROM mysql_test.customers;

			- 计算列值

				- SELECT cust_name,sex,cust_id+100 FROM mysql_test.customers;

			- 聚合函数

- 复制表

	- CREATE TABLE table_name2 like table_name;

INSERT INTO table_name2 select * from table_name;

- 多表查询

	- 交叉查询

		- SELECT * FROM tbl1 CROSS JOIN tbl2; 

		- SELECT * FROM tbl1,tbl2;

	- 内连接

		- 目的

			- 消除交叉连接的某些数据行

		- 使用 INNER JOIN 或 JOIN

		- SELECT * FROM table_name INNER JOIN table_name2 ON condition;

		- 使用场景

			- 等值连接

			- 非等值连接

			- 自连接

	- 外连接

		- 左外连接

			- LEFT [OUTER] JOIN

			- 包括左表里面的所有元祖，但在右表里面不匹配的行

		- 右外连接

			- RIGHT [OUTER] JOIN

			- 包括右表里面的所有元祖，但在左表里面不匹配的行

- WHERE 过滤行

	- WHERE 子句在分组和聚合之前过滤行，不可以包含聚合函数。

	- 比较运算

	- 范围判断

		- BETWEEN 100 AND 102

		- IN (100, 99, 98)

	- 判定空值

		- IS NULL

	- 子查询

		- SELECT Sno, Sname from Student WHERE Sno IN (SELECT Sno from SC WHERE grade > 80);

		- 比较运算

			- 比较运算符

				- expression {=|<|<=|>|>=|<=>|<>|!=}{ALL|SOME|ANY}(subquery)

				- ALL

					- 用于指定表达式需要与子查询结果集中的每个值进行比较

					- 查询工资高于部门编号为 2 的员工的工资的员工：

SELECT EmpName
FROM Employee
WHERE Salary > ALL (SELECT Salary FROM Employee WHERE DeptID = 2);

				- SOME/ANY

					- 表示只要表达式与子查询结果集中任意值满足关系时，就返回 TRUE

					- 查询工资高于任何一个部门编号为 2 员工的工资的员工：

SELECT EmpName
FROM Employee
WHERE Salary > ANY (SELECT Salary FROM Employee WHERE DeptID = 2);

		- EXISTS

			- 查询所有有选课的学生姓名

SELECT Sname FROM Student WHERE EXISTS (SELECT 1 FROM SC WHERE Student.Sno = SC.Sno);

- GROUP BY

	- GROUP BY ｛col_name|expr|position｝[ASC|DESC],…[WITH ROLLUP]

	- GROUP BY 子句可以包含任意数目的列，使得其可对分组进行嵌套

		- SELECT Department, JobTitle, COUNT(*)
FROM Employees
GROUP BY Department, JobTitle;

查询结果有三列：Department、JobTitle、COUNT(*)

在这个示例中，查询首先按 Department 分组，然后在每个部门内按 JobTitle 分组。

	- 嵌套分组的顺序和汇总

		- SELECT Department, JobTitle, SUM(Salary)
FROM Employees
GROUP BY Department, JobTitle WITH ROLLUP;


在这个示例中，汇总首先按 Department 分组，然后在每个部门内按 JobTitle 分组，并在最后生成一个完全汇总行。

	- GROUP BY 子句中的列必须是检索列或有效的表达式，但不能是聚合函数

		- SELECT Department, JobTitle, COUNT(*)
FROM Employees
GROUP BY Department, JobTitle;

		- SELECT Department, SUM(Salary)
FROM Employees
GROUP BY SUM(Salary); -- 错误，SUM 是聚合函数，不能用在 GROUP BY 中

	- 除聚合函数外，SELECT 语句中的每个列都必须在 GROUP BY 子句中给出

		- SELECT Department, JobTitle, COUNT(*)
FROM Employees
GROUP BY Department, JobTitle;

		- 错误语句：

SELECT Department, JobTitle, COUNT(*)
FROM Employees
GROUP BY Department;

	- 如果 Department 列中有 NULL 值，那么结果集中会有一个 NULL 分组。

		- SELECT Department, COUNT(*)
FROM Employees
GROUP BY Department;

- HAVING 过滤组

	- 用于聚合结果的过滤：HAVING 子句通常与聚合函数一起使用，如 SUM、AVG、MAX、MIN 和 COUNT。

	- HAVING 子句经常与 GROUP BY 子句结合使用，以过滤分组后的结果。

	- HAVING 子句在分组和聚合之后过滤分组，可以包含聚合函数。

	- SELECT Region, SUM(Amount) as TotalSales
FROM Sales
GROUP BY Region
HAVING SUM(Amount) > 500;

查询每个区域的总销售额，并只显示总销售额大于 500 的区域：

- ORDER BY

	- SELECT column1, column2, ...
FROM table_name
ORDER BY column1 [ASC|DESC], column2 [ASC|DESC], ...;

- LIMIT

	- LIMIT {[offset,] row_count|row_count OFFSET offset}

	- OFFSET 默认为 0 

### 视图

- 外模式对应到数据库中的概念是视图。 视图是数据库中的一个对象，是数据库管理系统提供给用户的以多种角度观察数据库中数据的一种重要机制

- 视图不是真实的表，是一张虚拟表，其本身并不存储数据。

- 优点

	- 集中分散数据

	- 简化查询语句

	- 重用 SQL 语句

	- 保护数据安全

	- 共享所需数据

	- 更改数据格式

- 创建视图

	- CREATE VIEW view_name[(column_list)] AS select_statement [WITH [CASCADED|LOCAL] CHECK OPTION]

- 查看已有视图

	- SHOW CREATE VIEW view_name

- 视图不能基于有聚合、分组、子查询、连接等的表。视图可以基于多个基本表，但是每次更新视图表只能更新一个基本表的数据，基于多个基本表的视图不能使用删除语句。

- 应用场景

	- 利用视图简化复杂的表连接

	- 使用视图重新格式化检索出的数据

	- 使用视图过滤不想要的数据

## 第五章：数据库编程

### 存储过程

- 概念

	- 重用代码，将固定的操作集合起来，由数据库服务器来完成， 实现某个特定任务。

存储过程是一组为了完成某项特定功能的 SQL 语句集， 可以由声明式的 SQL 语句和过程式的 SQL 语句组成。 这组语句经过编译后存储在数据库中，用户通过指定存储过程的名字和参数来调用并执行存储过程，而不必重新编译

	-  一个存储过程是一个可编程的函数，同时可看作是在数据库编程中对面向对象方法的模拟，他允许控制数据的访问方式， 当希望在不同的应用程序或平台上执行相同的特定功能时存储过程尤为合适

-  好处

	-  可增强 SQL 语言的功能和灵活性

	-  良好的封装性

	-  高性能

	-  可减少网络流量

	-  存储过程，作为一种安全机制来确保数据库的安全性和数据的完整性

-  创建存储过程

	- 使用 DELIMITER 命令可以避免 MySQL 在解析过程中误认为存储过程定义已经结束

	- DELIMITER //

CREATE PROCEDURE Calculate(IN num1 INT, IN num2 INT, OUT sum INT, INOUT difference INT)
BEGIN
    -- 计算和并返回
    SET sum = num1 + num2;
    -- 计算差并返回
    SET difference = num1 - num2;
END //

DELIMITER ;

	- -- 定义变量以接收输出
SET @sum = 0;
SET @difference = 0;

-- 调用存储过程
CALL Calculate(10, 5, @sum, @difference);

-- 获取输出值
SELECT @sum, @difference;  -- 输出 @sum 为 15，@difference 为 5

- 声明局部变量

	- 在存储过程体中声明局部变量使用 DECLARE 语句，格式如下：

DELIMITER //

CREATE PROCEDURE CalculateFactorial(IN n INT, OUT result INT)
BEGIN
    DECLARE i INT DEFAULT 1;      -- 计数器
    DECLARE factorial INT DEFAULT 1;  -- 用于存储阶乘结果

    -- 循环计算阶乘
    WHILE i <= n DO
        SET factorial = factorial * i;
        SET i = i + 1;
    END WHILE;

    -- 返回计算结果
    SET result = factorial;
END //

DELIMITER ;

	- 注意事项

		- 声明位置：局部变量必须在存储过程的 BEGIN 块中声明，且必须位于其他任何 SQL 语句之前。

		- 作用范围：局部变量的作用范围仅限于声明它们的存储过程体。在存储过程之外无法访问这些变量。

		- 初始化：局部变量可以在声明时使用 DEFAULT 子句进行初始化，也可以在存储过程体内通过 SET 语句进行赋值。

- SELECT 语句与局部变量

	- SELECT ... INTO 语句在 MySQL 中用于将查询结果存储到变量中，通常用于存储过程和触发器中。

	- DELIMITER //

CREATE PROCEDURE GetEmployeeInfo(IN emp_id INT, OUT emp_name VARCHAR(50), OUT emp_salary DECIMAL(10, 2))
BEGIN
    DECLARE name VARCHAR(50);
    DECLARE salary DECIMAL(10, 2);

    -- 使用 SELECT ... INTO 将查询结果存储到多个局部变量
    SELECT name, salary INTO name, salary
    FROM employees
    WHERE id = emp_id;

    -- 将局部变量的值赋给输出参数
    SET emp_name = name;
    SET emp_salary = salary;
END //

DELIMITER ;

	- -- 定义变量以接收输出
SET @name = '';
SET @salary = 0;

-- 调用存储过程
CALL GetEmployeeInfo(2, @name, @salary);

-- 查看结果
SELECT @name, @salary;

	- 注意事项

		- 单行结果：SELECT ... INTO 语句期望查询结果是单行。如果查询返回多行，会产生错误。

		- 变量类型：局部变量的数据类型应与查询结果的列类型兼容。

		- 错误处理：如果查询不返回任何结果，未找到的情况可能会导致变量保持其默认值或产生错误，可以结合条件语句处理这种情况。

- 过程式 SQL 语句

	- 概念

		- 允许在 SQL 语句中使用控制结构（如条件语句、循环、变量等）以编写复杂的业务逻辑

	- 主要特点

		- 控制结构：包括条件语句（如 IF...THEN...ELSE）、循环语句（如 WHILE、LOOP、REPEAT）等。

		- 变量和常量：允许声明和使用局部变量和常量。

		- 过程和函数：可以创建和调用存储过程和函数。

		- 异常处理

	- IF 语句

		- IF total_sales > 5000 THEN
    SET discount = 0.1;
ELSE
    SET discount = 0.05;
END IF;

	- CASE 语句

		- CASE
    WHEN grade = 'A' THEN SET bonus = 1000;
    WHEN grade = 'B' THEN SET bonus = 500;
    ELSE SET bonus = 100;
END CASE;

	- REPEAT 语句

		- DECLARE i INT DEFAULT 1;
REPEAT
    SET total_sales = total_sales + i;
    SET i = i + 1;
UNTIL i > 10
END REPEAT;

	- LOOP 语句

		- DECLARE i INT DEFAULT 1;
my_loop: LOOP
    SET total_sales = total_sales + i;
    SET i = i + 1;
    IF i > 10 THEN
        LEAVE my_loop;
    END IF;
END LOOP;

	- CURSOR 游标

		- 游标用于逐行处理查询结果集

游标相当于一个指针，指向当前一行数据

游标只能用于存储过程或函数中，可以定义多个游标，但是在一个 BEGIN…END语句块中每一个游标的名字必须是唯一的

游标不是一条SELECT语句，是被SELECT语句检索出来的结果集

		- 声明游标

			- DECLARE cursor_name CURSOR FOR SELECT employee_id, employee_name FROM employees;

		- 打开游标

			- OPEN cursor_name;

		- 获取游标中的数据

			- FETCH cursor_name INTO variable1, variable2, ...;

		- 关闭游标

			- CLOSE cursor_name;

		- 查找异常处理

			-     -- 声明 CONTINUE HANDLER 处理 NOT FOUND 条件
    DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = 1;

- 查看存储过程

	- 显示所有存储过程

		- SHOW PROCEDURE STATUS;

	- 查看存储过程的创建语句

		- SHOW CREATE PROCEDURE procedure_name;

- 删除存储过程

	- DROP PROCEDURE [IF EXISTS] procedure_name

### 存储函数

- DELIMITER //

CREATE FUNCTION calculate_bonus(salary DECIMAL(10, 2)) RETURNS DECIMAL(10, 2)
BEGIN
    DECLARE bonus DECIMAL(10, 2);
    SET bonus = salary * 0.10;
    RETURN bonus;
END //

DELIMITER ;

- SELECT calculate_bonus(50000.00);

### 存储过程和存储函数

- 相同点

	- 封装逻辑：存储过程和存储函数都可以封装复杂的业务逻辑和数据操作，减少代码重复，提高代码可维护性。

	- 参数支持：两者都可以接受参数。存储过程可以有输入参数（IN）、输出参数（OUT）和输入输出参数（INOUT），存储函数则只有输入参数（IN）。

	- 编译和缓存：两者在第一次调用时会被编译，并且编译后的代码可以被缓存以提高性能。

- 不同点

	- 返回值：

		- 存储过程：不返回值，除非通过输出参数（OUT 或 INOUT 参数）返回。

		- 存储函数：必须返回一个单一值，通过 RETURN 语句返回。

	- 调用方式：

		- 存储过程：通过 CALL 语句调用。例如：CALL procedure_name(parameters);

		- 存储函数：可以在 SQL 语句中使用，如在 SELECT、WHERE、SET 等语句中。例如：SELECT function_name(parameters);

	- 使用场景：

		- 存储过程：通常用于执行一系列数据库操作，可以包含多个步骤和复杂的逻辑。适用于需要执行多项操作的任务。

		- 存储函数：通常用于计算和返回一个值，适用于需要在查询中嵌入计算逻辑的情况。

## 第六章：数据库安全与保护

### 数据库完整性

- 指数据库中数据的正确性和相容性

- 数据库的安全保护功能

	- 完整性控制

	- 安全性控制

	- 并发控制

	- 数据库备份与恢复

- 数据完整性约束

	- 数据完整性约束是为了防止数据库中存在不符合语义的数据，为了维护数据的完整性，DBMS 必须提供一种机制来检查数据库中的数据，以判断其是否满足语义规定的条件

	- DBMS 检查数据是否满足完整性约束条件的机制称为完整性检查

	- 完整性

		- 实体完整性

			- 主键约束：PRIMARY KEY

			- 候选键约束：UNIQUE KEY

		- 参照完整性

			- 通过创建表（CREATE TABLE）或更新表（ALTER TABLE）的同时定义一个外键声明来实现

		- 用户定义的完整性

			- 非空约束：NOT NULL；

			- CHECK 约束：可以对列或表进行约束

				- check (expr)

				- expression 可以是表达式，也可以是子查询

			- 触发器

		- 外键声明

			- 两种方式

				- 在某列的属性定义后加上外键约束

				- 在所有列定义后添加外键约束

			- 外键定义的语法

				- REFERENCES table_name(column_name,column_name2) [ON DELETE reference_option] [ON UPDATE reference_option]

				- column_name 语法

					- column_name[(length)] [ASC|DESC]

				- reference_option 语法

					- RESTRICT|CASCADE|SET NULL|NO ACTION

			- 定义外键的规则

				- 被参照表必须是已经创建的表，或者是当前正在创建的表（自参照表）

				- 必须为被参照表定义主键

				- 必须在被参照表的表名后面指定列名或列名的组合，并且必须是参照表的主键或候选键

				- 外键的非空值必须出现在指定的主键中

				- 外键中的列的数目必须和被参照表的主键列的数目相同，数据类型也必须相同

	- 约束

		- 列级约束

			- 对数据类型的约束

			- 对数据格式的约束

			- 对取值范围或取值集合的约束

			- 对空值的约束

		- 元组约束

			- 指元组中各个字段之间的相互约束

		- 表级约束

			- 指若干元组之间，关系之间的联系的约束

		- 命名完整性约束

			- 基于表的完整性约束

				- CONSTRAINT [symbol]

					- symbol 必须在数据库范围内唯一

		- 更新完整性约束

			- 使用 ALTER TABLE 来更新表中的有关约束，可以使用 ADD CONSTRAINT 来添加约束

			- 完整性约束不能直接被修改，需要先删除约束，再重新添加约束

			- 使用 ALTER TABLE 可以删除表的约束同时保留表结构

			- 使用 DROP TABLE 会删除表的所有

	- 候选键与主键之间存在以下⼏点区别

		- ⼀个表中只能创建⼀个主键，但可以定义若⼲个候选键

		- 定义主键约束时，系统会⾃动产⽣ PRIMARY KEY 索引，而定义候选键时，系统自动产生 UNIQUE KEY 索引

### 触发器

- 一类由事件驱动的数据库对象，也是一种保证数据完整性的方法

- 作用

	- 实现主键和外键不能保证的复杂的参照完整性和数据一致性，从而有效保护表中数据

- 语法

	- CREATE TRIGGER trigger_name trigger_time trigger_event ON table_name FOE EACH ROW trigger_body

		- trigger_time

			- BEFORE

			- AFTER

		- trigger_event

			- INSERT

			- UPDATE

			- DELETE

		- FOR EACH ROW

			- 指定对于受触发事件影响的每一行都要激活触发器的动作

		- trigger_body

			- 指定触发器激活时将要执行的MySQL语句，如果要执行多个语句，可使用BEGIN…END复合语句结构

- 每个表最多定义 6 个触发器

- 删除触发器

	- DROP TRIGGER [IF EXISTS] [db_name.]trigger_name;

- 触发器如果要修改，需要先删除，再创建

- 触发器使用

	- INSERT

		- 在 INSERT 触发器代码内，可引用一个名为 NEW（不区分大小写）的虚拟表来访问被插入的行

		- 在 BEFORE INSERT 的触发器中，NEW 中的值可以被更新

		- 对于 AUTO_INCREMENT 列，NEW 在 INSERT 执行之前包含的值是 0，在 INSERT 执行之后将包含新的自动生成值

	- DELETE

		- 在 DELETE 触发器代码内，可以引用一个名为 OLD（不区分大小写）的虚拟表来访问被删除的行

		- OLD 中的值全部是只读的，不能被更新

	- UPDATE

		- 在 UPDATE 触发器代码内，可以引用一个名为OLD（不区分大小写）的虚拟表来访问以前的值，也可引用一个名为 NEW（不区分大小写）的虚拟表来访问新更新的值

		- 在 BEFORE UPDATE 触发器中，NEW 中的值可以被更新

		- OLD 中的值全部是只读的，不能被更新

		- 当触发器涉及触发表自身的更新操作时，只能使用 BEFORE UPDATE，不能使用 AFTER UPDATE

### 安全性与访问控制

- 数据库的安全性是指保护数据库以防止不合法的使用而造成数据泄露、更改或破坏

- 数据库系统对数据的安全管理是使用身份验证、数据库用户权限确认等访问控制措施

- 创建用户账号

	- CREATE USER user[IDENTIFIED BY [PASSWORD] `password`];

		- user：指定创建用户账户，其格式为user_name@host_name。其中 user_name 表示用户名，host_name 表示主机名。如果没有指定主机名，则主机名会默认为%，表示一组主机

		- IDENTIFIED BY：指定用户账户对应的口令

		- PASSWORD：指定散列口令（散列口令可通过 PASSWORD 函数获得）- 旧版本可用

		- password：指定用户账号的口令（明文或散列口令）

	- 注意

		- 要使用 CREATE USER 语句，必须拥有 MySQL 中 mysql 数据库的 INSERT 权限或全局 CREATE USER 权限

		- 使用 CREATE USER 语句创建一个用户账户后，会在系统自身的 mysql 数据库的 user 表中添加一条新记录

		- 如果两个用户具有相同的用户名和不同的主机名，MySQL 会将它们视为 不同的用户，并允许为这两个用户分配不同的权限集合

		- 如果在 CREATE USER 语句的使用中，没有为用户指定口令，那么 MySQL允许该用户可以不使用口令登录系统

		- 新创建的用户拥有的权限很少

- 删除用户账号

	- DROP USER user[,user]…

	- DROP USER 语句可用于删除一个或多个 MySQL 账户，并消除其权限

	- 要使用 DROP USER 语句，必须拥有 MySQL 中mysql 数据库的 DELETE 权限或全局 CREATE USER 权限

	- 在 DROP USER 语句的使用中，如果没有明确地给出账户的主机名，则该主机名会默认为 %

	- 用户的删除不会影响到他们之前所创建的表、索引或其他数据库对象

- 修改用户账号

	- RENAME USER old_user TO new_user[,old_user TO new_user]…

		- old_user：指定系统中已经存在的 MySQL 用户 账号

		- new_user：指定新的 MySQL 用户账户

	- RENAME USER 语句用于对原有 MySQL 账户进行重命名

	- 要使用 RENAME USER 语句，必须拥有 MySQL 中 mysql 数据库的 UPDATE 权限或全局 CREATE USER 权限

	- 如果系统中旧账户不存在或新账户已存在，则语句执行会出现错误

- 修改用户密码

	- 旧版 MySQL

		- SET PASSWORD [FOR user] = [PASSWORD('new_pwd')|'encrypted password']

	- 新版 MySQL

		- SET PASSWORD FOR 'user'@'host' = 'new_pwd';

- 查看用户权限

	- SHOW GRANTS FOR 'user'@'host'

	- USAGE ON *.* 表示没有任何权限

- 权限授予

	- GRANT priv_type[(column_list)] [,priv_type[(column_list)]] ON [object_type] priv_level TO user_specification[,user_specification] [WITH GRANT OPTION]

		- 授予表权限 priv_type 可选项

			- SELECT

			- INSERT

			- DELETE

			- UPDATE

			- REFERENCES

			- CREATE

			- ALTER

			- INDEX

			- DROP

			- ALL|ALL PRIVILIGES

		- 授予列权限时，priv_type 只能是

			- SELECT(col_name[,col_name])

			- INSERT(col_name[,col_name])

			- UPDATE(col_name[,col_name])

		- 授予数据库权限 priv_type 可选项

			- SELECT

			- INSERT

			- DELETE

			- UPDATE

			- REFERENCES

			- CREATE

			- ALTER

			- INDEX

			- DROP

			- CREATE TEMPORARY TABLES

			- CREATE VIEW

			- SHOW VIEW

			- CREATE ROUTINE

			- ALTER ROUTINE

			- EXECUTE ROUTINE

			- LOCK TABLES

			- ALL|ALL PRIVILIGES

			- CREATE USER

			- SHOW DATABASES

	- GRANT SELECT (name, address), UPDATE (name, address)
ON TABLE mydb.employees
TO 'alice'@'localhost'
WITH GRANT OPTION;

		- 授予 alice 对 mydb 数据库中 employees 表的 name 和 address 列的 SELECT 和 UPDATE 权限。

允许 alice 将她拥有的权限授予其他用户。

	- 旧版 MySQL 中，当 TO 'user'@'host' 中的 user 不存在时，会自动创建 user, 所以 GRANT 语句也可以用来创建 user

	- GRANT ALL ON mysql_test.* TO 'wangwu'@'localhost' ;

		- 授予 'wangwu'@'localhost' 所有权限

	- GRANT CREATE USER ON *.* TO 'wangwu'@'localhost' ;

		- 授予系统中已存在用户 wangwu 拥有创建用户的权限

- 权限撤销

	- REVOKE priv_type[(column_list)] [,priv_type[(column_list)]] ON [object_type] priv_level FROM user_specification[,user_specification]

	- REVOKE ALL PRIVILEGES, GRANT OPTION FROM user [, user];

		- 回收特定用户的所有权限

	- 权限撤销必须拥有全局 CREATE/UPDATE USER 权限

### 事务与并发控制

- 事务

	- 事务是用户定义的一个数据操作序列，这些操作可作为一个完整的工作单元，要么全部执行，要么全部不执行，是一个不可分割的工作。

	- 显示定义

		- BEGIN TRANSCATION

		- COMMIT

		- ROLLBACK

	- 四个特征

		- Atomicity

			- 保证事务包含的一组更新操作是原子不可分的，即事务是不可分割的最小工作单位，所包含的这些操作是一个整体

		- Consistency

			- 要求事务必须满足数据库的完整性约束，且事务执行完毕后将数据库由一个一致性状态转变为另一个一致性状态

一致性和原子性密切相关

		- Isolation

			- 隔离性要求事务是彼此独立的、 隔离的， 即一个事务的执行不能被其他事务所干扰，一个事务对数据库变更的结果必须在它 COMMIT 后，另一个事务才能存取

		- Durability

			- 持续性也称为永久性(Permanence)，是指一个事务一旦提交，它对数据库中数据的改变就应该是永久性的，且接下来的其他操作或故障不应该对其执行结果有任何影响。

- 并发控制

	- 事务是并发控制的基本单位

	- 并发操作问题

		- 丢失更新

		- 不可重复读

		- 读脏数据

	- 并发问题解决办法

		- 封锁

			- 通常以粒度来描述封锁的数据单元的大小，粒度越细，并发性就越大， 但软件复杂性和系统开销也就越大。

			- 分类

				- 排他锁(Exclusive Lock, X锁）

					- 写

				- 共享（share Lock，S锁）

					- 读

			- 级别

				- 0 级封锁

					- 封锁的事务不重写其他非 0 级封锁事务的未提交的更新数据

				- 1 级封锁

					- 被封锁的事务不允许重写未提交的更新数据

				- 2 级封锁

					- 被封锁的事务既不重写也不读未提交的更新数据

				- 3 级封锁

					- 被封锁的事务不读未提交的更新数据，不写任何（包括读操作的）未提交数据

			- 活锁

				- 事务因为优先级低而永远处于等待状态

			- 死锁

				- 两个以上事务循环等待被同组中另一事务锁住的数据单元的情形

				- 解决办法

					- 一次性锁请求

					- 锁请求排序

					- 序列化处理

		- 时间戳

		- 乐观控制法

		- 多版本并发控制

	- 可串行性

		- 一组事务的调度就是它们的基本操作的一种排序

	- 两段封锁法

		- 封锁是一种并发控制技术，可串行性是并发控制的正确性标准。两段封锁法是一种简单有效的保障封锁调度和可串行性的方法

		- 发展（Growing）阶段/加锁阶段

		- 收缩（Shrinking）阶段/释放锁阶段

### 备份与恢复

- 可能会造成数据库运行事务异常终端的因素

	- 计算机硬件故障

	- 计算机软件故障

	- 病毒

	- 人为误操作

	- 自然灾害

	- 盗窃

- 数据库备份

	- 通过导出数据或者复制表文件的方式来制作数据库的复本

- 数据库恢复

	- 当数据库出现故障或遭到破坏时，将备份的数据库加载到系统，从而使数据库从错误状态恢复到备份时的正确状态

- 数据库的恢复是以备份为基础的，它是与备份相对应的系统维护和管理操作

- 数据备份

	- SELECT * FROM table_name
INTO OUTFILE 'file_name'
FIELDS TERMINATED BY ','
OPTIONALLY ENCLOSED BY '"'
LINES TERMINATED BY '\n';

		- FIELDS TERMINATED BY ',': 指定字段分隔符，这里使用逗号。

		- OPTIONALLY ENCLOSED BY '"': 字段值可选地由引号包围。

		- LINES TERMINATED BY '\n': 指定行分隔符，这里使用换行符。

	- SELECT blob_column FROM table_name WHERE condition
INTO DUMPFILE 'file_name';

		- 这条命令适用于处理不需要分隔的大型二进制对象（BLOB），例如，从数据库中导出图像文件。

- 数据恢复

	- LOAD DATA INFILE 'file_name'
INTO TABLE tbl_name
[FIELDS
    [TERMINATED BY 'string']
    [[OPTIONALLY] ENCLOSED BY 'char']
    [ESCAPED BY 'char']
]
[LINES
    [STARTING BY 'string']
    [TERMINATED BY 'string']
];


	- LOAD DATA INFILE '/path/to/data.csv'
INTO TABLE my_table
FIELDS TERMINATED BY ','
OPTIONALLY ENCLOSED BY '"'
LINES TERMINATED BY '\n';

		- 这个命令将 data.csv 中的数据导入到 my_table 表中，字段通过逗号分隔，且字段内容可能被引号包围。此命令假设每条记录占一行，以换行符结束。

## 第七章：数据库应用设计与开发实例

### 需求描述与分析

- 数据库应用系统的设计与实现

	- 以数据库的生命周期为演化主线，数据库应用软 件的设计与开发过程可由需求分析、系统功能与 数据库的设计、系统功能与数据库的实现、测试 与维护等阶段构成。

### 系统设计

### 系统实现

### 系统测试与维护

## 第八章：数据管理技术的发展

### 数据管理技术的发展

- 以数据建模和数据库管理系统核心技术为主，已成为了核心技术和重要基础

- 数据模型是数据库系统的核心和基础

- 网状、层次 -> 关系数据库 -> 新一代数据库

- IMS

	- 1969 年  IBM 研制的层次模型

- DBTG

	- 基于网状结构，是网状模型数据库系统的典型代表

- 第三代数据库系统应具有的三个基本特征

	- 支持数据管理，对象管理和知识管理
具有面向对象模型的基本特征

	- 保持或继承第二代数据库系统的技术

	- 必须对其他系统开放

### 数据仓库

- 计算机系统中存在着两类不同的数据处理工作

	- 操作型处理（OLTP）

		- 传统的数据库技术为操作型处理服务

	- 分析型处理（OLAP）

		- 数据仓库为分析型处理

- 定义

	- 面向分析的数据存储方案

用于支持决策

按照决策主题选择数据并以新的数据模型存储

- 特征

	- 面向主题

	- 集成性

	- 数据的非易失性

	- 数据的时变性

- 概念

	- 粒度

		- 粒度是指数据仓库的数据单位中保存数据的细化或综合程度的级别，细化程度越高，粒度级就越小

	- 分割

		- 分割是将数据分散到各自的物理单元中，以便能分别处理，以提高数据处理的效率

		- 分割后的单元叫做切片

	- 维

		- 维是人们观察数据的特定角度，是考虑问题时的一类属性

### 数据挖掘

- 数据库中的知识发现（KDD）

- 功能

	- 概念描述：归纳数据的某些特征

	- 关联分析：找出数据库隐藏的关联网

	- 分类与预测：决策树模型、神经网络模型、
线性回归模型

	- 聚类：按相似性归纳若干类别

	- 孤立点检测

	- 趋势和演变分析

- 挖掘过程

	- 确定业务对象

	- 数据的选择

	- 数据的预处理

	- 建模

	- 模型评估

	- 模型部署

### 大数据管理技术

- 大数据被称为未来的新石油

- 一搬在 10TB 左右

- 大量化（volume）

- 多样化（Variety）

- 快速化（velocity）

- 真实性（verity）

- 特征

	- 大量化

		- 海量数据，TB 到 PB

	- 多样化

		- 种类繁多，编码方式、数据格式、应用特征等方面存在差异

	- 快速化

		- 数据处理的效率就是企业的竞争力

	- 价值密度低

		- 价值密度的高低与数据总量的大小成反比

- 分布式文件系统（HDFS）

	- 随机选择存储位置

	- 强大的容错能力

- NoSQL

	- NoSQL 系统为了提高存储能力和并发读写能力采用了极其简单的数据模型，支持简单的查询操作，而将复杂操作留给应用层实现。

通过大量节点的并行处理获得高性能

	- 两种解释

		- non-relational

		- Not Only SQL

	- 模型

		- 键值模型

			- 是 NoSQL 采用最多的数据存储方式

使用哈希函数实现快速映射

		- 文档模型

			- 可以实现比键值模型更复杂的查询条件

		- 列模型

			- 以列为单位存储数据

		- 图模型

			- 基于图理论，使用节点、属性和边的概念

	- MapReduce

		- 主要应用于大规模廉价集群上的大数据并行处理

