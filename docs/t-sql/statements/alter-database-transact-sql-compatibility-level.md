---
title: "ALTER DATABASE 兼容级别 (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 08/07/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- COMPATIBILITY_LEVEL_TSQL
- COMPATIBILITY_LEVEL
dev_langs:
- TSQL
helpviewer_keywords:
- 80 compatibility level
- ALTER DATABASE statement, compatibility levels
- 90 compatibility level
- compatibility levels [SQL Server]
- 100 compatibility level
ms.assetid: ca5fd220-d5ea-4182-8950-55d4101a86f6
caps.latest.revision: 89
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 7b65511b09f2a94d30c39c1f97ed88cfbfab855b
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="alter-database-transact-sql-compatibility-level"></a>ALTER DATABASE (Transact SQL) 兼容性级别
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  
将某些数据库行为设置为与指定的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 版本兼容。 有关其他 ALTER DATABASE 选项，请参阅[ALTER DATABASE &#40;Transact SQL &#41;](../../t-sql/statements/alter-database-transact-sql.md).  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
ALTER DATABASE database_name   
SET COMPATIBILITY_LEVEL = { 140 | 130 | 120 | 110 | 100 | 90 }  
```  
  
## <a name="arguments"></a>参数  
 *database_name*  
 要修改的数据库的名称。  
  
 COMPATIBILITY_LEVEL {140 | 130 | 120 | 110 | 100 | 90 | 80}  
 要使数据库与之兼容的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 版本。 可以配置以下的兼容性级别值：  
  
|Product|数据库引擎版本|兼容性级别指定内容|支持的兼容性级别值|  
|-------------|-----------------------------|-------------------------------------|------------------------------------------|  
|[!INCLUDE[ssSQLv14_md](../../includes/sssqlv14-md.md)]|14|140|140, 130, 120, 110, 100|
|[!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]|12|130|140, 130, 120, 110, 100|  
|[!INCLUDE[ssSQL15](../../includes/sssql15-md.md)]|13|130|130, 120, 110, 100|  
|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|12|120|120, 110, 100|  
|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]|11|110|110, 100, 90|  
|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]|10.5|100|100, 90, 80|  
|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|10|100|100, 90, 80|  
|SQL Server 2005|9|90|90, 80|  
|SQL Server 2000|8|80|80|  
  
> [!NOTE]  
>  **Azure SQL 数据库**V12 已于 2014 年 12 月发布。 该版本的一个方面在于新创建的数据库，必须设置为 120 其兼容级别。 在 2015 SQL 数据库开始级别 130 的支持，尽管默认值保持 120。  
> 
> 从开始**2016 年 6 月中旬**，Azure SQL 数据库中的默认兼容性级别都而不是 120 130**新创建的**数据库。 在 2016 年 6 月中旬之前创建的现有数据库不受影响，并维护其当前的兼容性级别 （100、 110 或 120）。 
> 
> 如果你为你的数据库中通常情况下，想级别 130 但有理由首选级别 110**基数估计**算法，请参阅[ALTER DATABASE SCOPED CONFIGURATION &#40;Transact SQL &#41;](../../t-sql/statements/alter-database-scoped-configuration-transact-sql.md)，，尤其其关键字 LEGACY_CARDINALITY_ESTIMATION = ON。  
>  
>  有关如何评估的最重要的查询，在 Azure SQL 数据库上的两个兼容性级别之间的性能差异的详细信息，请参阅[与 Azure SQL 数据库中的兼容性级别 130 改进查询性能](http://azure.microsoft.com/documentation/articles/sql-database-compatibility-level-query-performance-130/)。


 执行以下查询以确定的版本[!INCLUDE[ssDE](../../includes/ssde-md.md)]连接到。  
  
```tsql  
SELECT SERVERPROPERTY('ProductVersion');  
```  
  
> [!NOTE]  
>  并非所有因兼容级别的功能支持对[!INCLUDE[ssSDS](../../includes/sssds-md.md)]。  

 若要确定当前的兼容性级别，请查询**compatibility_level**列[sys.databases &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md).  
  
```tsql  
SELECT name, compatibility_level FROM sys.databases;  
```  
  
## <a name="remarks"></a>注释  
 对于的所有安装[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]，默认兼容级别设置为的新版[!INCLUDE[ssDE](../../includes/ssde-md.md)]。 数据库设置为此级别，除非**模型**数据库具有较低的兼容性级别。 当从任何早期版本升级数据库[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]，数据库将保留其现有的兼容性级别，如果它是至少最小实例允许[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]。 升级的数据库的兼容性级别低于允许的级别，可将数据库设置为级别允许的最低兼容性。 这既适用于系统数据库也适用于用户数据库。 使用**ALTER DATABASE**若要更改数据库的兼容性级别。 若要查看数据库的当前兼容级别，查询**compatibility_level**中的列**sys.databases**目录视图。  

  
## <a name="using-compatibility-level-for-backward-compatibility"></a>利用兼容性级别获得向后兼容  
 兼容性级别只影响指定数据库的行为，而不影响整个服务器的行为。 兼容性级别只实现与 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的早期版本保持部分向后兼容。 从兼容性模式 130 开始，任何新的查询计划影响功能已添加到新的兼容性模式。 这样做是为了在由于查询计划更改导致性能下降而引发的升级过程的风险降至最低。 从应用程序的角度看，目标将仍是最新兼容性级别以便继承某些新功能，以及为在查询优化器空间中完成的性能改进，但为此，以可控方式。 通过将兼容性级别用作临时性的迁移辅助工具，可解决相关兼容性级别设置控制的行为之间存在的版本差异问题。 有关更多详细信息请参阅本文后面的部分升级的最佳做法。  
  
 如果现有[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]通过你的版本中的行为差异会影响应用程序[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]，将转换应用程序可以无缝的新的兼容性模式。 然后使用**ALTER DATABASE**兼容性级别更改为 130。 新数据库的兼容性设置时才生效**USE Database**发出或使用该数据库作为默认数据库处理新的登录名。  
  
## <a name="best-practices"></a>最佳实践  
 如果在用户连接到数据库时更改兼容性级别，可能会使活动查询产生不正确的结果集。 例如，如果在编写查询计划时兼容性级别发生更改，则编写后的计划可能同时基于旧的和新的兼容性级别，从而造成计划不正确，并可能导致结果不准确。 此外，如果将计划放在计划缓存中供后续的查询重用，则问题可能更加复杂。 为了避免查询结果不准确，建议您使用以下过程来更改数据库的兼容性级别：  
  
1.  通过使用 ALTER DATABASE SET SINGLE_USER，将数据库设置为单用户访问模式。  
  
2.  更改数据库的兼容性级别。  
  
3.  通过使用 ALTER DATABASE SET MULTI_USER，将数据库设为多用户访问模式。  
  
4.  有关设置数据库的访问模式的详细信息，请参阅[ALTER DATABASE &#40;Transact SQL &#41;](../../t-sql/statements/alter-database-transact-sql.md).  
  
## <a name="compatibility-levels-and-stored-procedures"></a>兼容性级别和存储过程  
 执行某一存储过程时，该存储过程将使用定义它的数据库的当前兼容性级别。 在更改某一数据库的兼容性设置时，该数据库的所有存储过程都将随之自动重新编写。  

## <a name="differences-between-compatibility-level-130-and-level-140"></a>兼容性级别 130 和级别 140 之间的差异  
本部分介绍与兼容性级别 140 引入的新行为。

|兼容性级别设置为 130 或更低|140 的兼容性级别设置|  
|--------------------------------------------------|-----------------------------------------|  
|基数估计的语句引用多语句表值函数使用固定的行猜测值。|基数估计的符合条件语句引用多语句表值函数将使用函数输出的实际基数。  这通过以下方式启用**交错执行**对于多语句表值函数。|
|请求内存不足的批处理模式下查询授予溢出到磁盘中的结果可能会继续对连续执行的问题的大小。|请求没有足够的内存授予大小溢出到磁盘中的结果可能提升性能上连续执行的批处理模式下查询。  这通过以下方式启用**批处理模式内存授予反馈**如果溢出引起的批处理模式运算符，这将更新缓存计划的内存授予大小。 |
|请求过多内存的批处理模式下查询授予导致并发问题可能会继续对连续执行的问题的大小。|请求过多内存的批处理模式下查询授予上连续执行的并发可能具有提高并发问题会导致的大小。  这通过以下方式启用**批处理模式内存授予反馈**如果最初请求过多，这将更新缓存计划的内存授予大小。|
|批处理模式下查询包含联接运算符可以获得三个物理联接算法，包括嵌套的循环、 哈希联接和合并联接。  如果基数估计不联接输入正确的则可以选择不适当的联接算法。  如果发生这种情况，性能将会降低，并且不适当的联接算法将保持正在使用，直到缓存的计划在重新编译。|包含调用的其他联接运算符**自适应联接**。 如果基数估计不正确的外部生成联接输入，则可以选择不适当的联接算法。  如果发生这种情况，并且该语句是适合自适应联接，嵌套的循环将用于较小的联接输入和哈希联接将用于较大的联接输入动态而无需重新编译。 |
|引用列存储索引的普通计划均不适合批处理模式执行。 |引用列存储索引的普通计划将丢弃适合批处理模式执行的计划。|
|Sp_execute_external_script UDX 运算符只能在行模式下运行。|Sp_execute_external_script UDX 运算符适合批处理模式执行。|  
|多语句 TVF 没有交错的执行 |对于多语句 Tvf 以提高计划质量的交错的执行。 |

修补程序时在 SQL Server 自 2017 年之前的 SQL Server 的早期版本中的跟踪标志 4199 下现在默认启用。 兼容性模式下 140。 跟踪标志 4199 仍将适用于新查询优化器修补程序将在 SQL Server 2017 后释放。 跟踪标志 4199 有关的信息，请参阅[Trace Flag 4199](https://support.microsoft.com/en-us/kb/974006)。  
  
## <a name="differences-between-compatibility-level-120-and-level-130"></a>兼容性级别 120 和级别 130 之间的差异  
本部分介绍中引入的兼容性级别 130 的新行为。   

  
|兼容性级别设置为 120 或更低|兼容性级别设置为 130|  
|--------------------------------------------------|-----------------------------------------|  
|Insert select 语句中的插入是单线程。|Insert select 语句中的插入是多线程，或者可以使用的并行计划。|  
|内存优化表的查询执行单线程。|内存优化表的查询现在可以并行计划。|  
|引入 SQL 2014 基数估计器**CardinalityEstimationModelVersion ="120"**|进一步基数估算 (CE) 改进基数估计模型 130 便可看到从查询与计划。 **CardinalityEstimationModelVersion ="130"**|  
|批处理模式与行模式更改，列存储索引<br /><br /> 具有列存储索引的表上的排序是在行模式中<br /><br /> 在如延隔时间或潜在客户的行模式下的开窗函数聚合操作<br /><br /> 与在行模式中运行的多个 distinct 子句的列存储表的查询<br /><br /> 运行在 MAXDOP 1 下或与在行模式下执行某一串行计划查询 | 批处理模式与行模式更改，列存储索引<br /><br /> 具有列存储索引的表上的排序现在都放在批处理模式<br /><br /> 开窗聚合现在运行在批处理模式下，例如延隔时间或主管<br /><br /> 对具有多个 distinct 子句的列存储表的查询以批处理模式运行<br /><br /> 运行下 Maxdop1 或与某一串行计划的查询以批处理模式执行|  
| 可以自动更新统计信息。 | 这将自动更新统计信息的逻辑是大型表更主动的。  在实践中，这应减少客户已经经常但其中不已更新统计信息以包含这些值，其中查询新插入的行的查询看到性能问题的情况。 |  
| 跟踪 2371年在默认情况下为 OFF [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]。 | [跟踪 2371年](https://blogs.msdn.microsoft.com/psssql/2016/10/04/default-auto-statistics-update-threshold-change-for-sql-server-2016/)在默认情况下为 ON [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)]。 跟踪标志 2371年告知自动统计信息更新程序要采样的行，具有很好的许多行的表中的较小但丝毫子集。 <br/> <br/> 一项重要改进是在此示例中包括更多最近插入的行。 <br/> <br/> 另一改进是让运行而更新统计信息过程是运行，而不阻塞查询的查询。 |  
| 级别 120，统计信息通过采样*单个*-线程过程。 | 对于级别 130，统计信息通过采样*多*-线程过程。 |  
| 253 传入的外键是的上限。 | 可以按最多 10,000 个传入的外键或类似引用引用某一给定的表。 有关限制，请参阅 [Create Foreign Key Relationships](../../relational-databases/tables/create-foreign-key-relationships.md)。 |  
|允许使用不推荐使用的 MD2、 MD4、 MD5、 SHA 和 SHA1 哈希算法。|允许使用唯一 SHA2_256 和 SHA2_512 哈希算法。|  
  
  
修补程序时在跟踪标志 4199 在早期版本的[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]之前[!INCLUDE[ssSQL15](../../includes/sssql15-md.md)]现在默认启用。 兼容性模式下 130。 跟踪标志 4199 仍将适用于之后发布的新查询优化器修补[!INCLUDE[ssSQL15](../../includes/sssql15-md.md)]。 若要使用在较旧的查询优化器[!INCLUDE[ssSDS](../../includes/sssds-md.md)]必须选择兼容性级别为 110。 跟踪标志 4199 有关的信息，请参阅[Trace Flag 4199](https://support.microsoft.com/en-us/kb/974006)。  
  
## <a name="differences-between-lower-compatibility-levels-and-level-120"></a>较低兼容性级别和级别 120 之间的差异  
 本节介绍随兼容性级别 120 引入的新行为。  
  
|兼容性级别设置为 110 或更低|兼容性级别设置为 120|  
|--------------------------------------------------|-----------------------------------------|  
|使用旧版查询优化器。|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] 包括了对创建和优化查询计划的组件的显著改进。 这个新的查询优化器功能依赖于使用数据库兼容性级别 120。 若要利用这些改进，应使用数据库兼容性级别 120 开发新的数据库应用程序。 应对从较早版本的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中迁移的应用程序进行仔细测试，以便确认保持或改进了好的性能。 如果性能下降，可以将数据库兼容性级别设置为 110 或更低，以便使用较早的查询优化器方法。<br /><br /> 数据库兼容级别 120 使用针对现代数据仓库和 OLTP 工作负荷进行优化的新基数估计器。 在设置之前数据库兼容性级别为 110 由于性能问题，请参阅的查询计划部分中的建议[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] [What's New in 数据库引擎](../../database-engine/configure-windows/what-s-new-in-sql-server-2016-database-engine.md)主题。|  
|在兼容性级别低于 120，语言设置时，将忽略转换**日期**为字符串值的值。 请注意，此行为是仅特定于**日期**类型。 请参阅下面的示例部分中的示例 B。|转换时，将不会忽略语言设置**日期**为字符串值的值。|  
|EXCEPT 子句右侧的递归引用产生无限循环。 下面的示例部分中的示例 C 演示此行为。|EXCEPT 子句中的递归引用产生遵从 ANSI SQL 标准的错误。|  
|递归 CTE 允许列名重复。|递归 CTE 不允许列名重复。|  
|如果更改触发器，则启用禁用的触发器。|更改触发器不更改触发器的状态（已启用或已禁用）。|  
|OUTPUT INTO 表子句忽略 IDENTITY_INSERT SETTING = OFF，并允许插入显式值。|将 IDENTITY_INSERT 设置为 OFF 后，不能为表中的标识列插入显式值。|  
|将数据库包含设置为部分包含后，验证 MERGE 语句的 OUTPUT 子句中的 $action 字段可能会返回排序规则错误。|MERGE 语句的 $action 子句返回的值的排序规则是数据库排序规则而非服务器排序规则，因此不会返回排序规则冲突错误。|  
|A **SELECT INTO**语句始终创建单线程方式插入操作。|A **SELECT INTO**语句可以创建并行插入操作。 插入大量行时，并行操作可提高性能。|  
  
## <a name="differences-between-lower-compatibility-levels-and-levels-110-and-120"></a>较低兼容性级别与级别 110 和 120 之间的差异  
 本节介绍随兼容性级别 110 引入的新行为。   此部分也适用于级别 120。  
  
|兼容性级别设置为 100 或更低|至少为 110 的兼容性级别设置|  
|--------------------------------------------------|--------------------------------------------------|  
|公共语言运行时 (CLR) 数据库对象用 CLR 的版本 4 执行。 但会避免在 CLR 的版本 4 中引入的某些行为更改。 有关详细信息，请参阅[What's New in CLR 集成](../../relational-databases/clr-integration/clr-integration-what-s-new.md)。|CLR 数据库对象用 CLR 的版本 4 执行。|  
|XQuery 函数**字符串长度**和**子字符串**计为两个字符的每个代理项。|XQuery 函数**字符串长度**和**子字符串**计数作为一个字符的每个代理项。|  
|在递归公用表表达式 (CTE) 查询中允许 PIVOT。 然而，当每个分组有多个行时，该查询返回不正确的结果。|在递归公用表表达式 (CTE) 查询中不允许 PIVOT。 将返回错误。|  
|RC4 算法仅用于支持向后兼容性。 仅当数据库兼容级别为 90 或 100 时，才能使用 RC4 或 RC4_128 对新材料进行加密。 （建议不要使用。）在 [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] 中，可以通过任何兼容性级别对使用 RC4 或 RC4_128 加密的材料进行解密。|不能使用 RC4 或 RC4_128 加密新材料。 而是使用一种较新的算法，如 AES 算法之一。 在 [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] 中，可以通过任何兼容性级别对使用 RC4 或 RC4_128 加密的材料进行解密。|  
|CAST 和 CONVERT 上的操作的默认样式**时间**和**datetime2**数据类型是 121 当在计算的列表达式中使用任一类型除外。 对于计算列，默认样式为 0。 当创建用于涉及自动参数化的查询中或约束定义中的计算列时，此行为会影响计算列。<br /><br /> 示例 D 中的下面的示例部分显示样式 0 和 121 之间的差异。 它并不演示上面所述的行为。 有关日期和时间的样式的详细信息，请参阅[CAST 和 CONVERT &#40;Transact SQL &#41;](../../t-sql/functions/cast-and-convert-transact-sql.md).|在兼容性级别 110，强制转换和转换操作的默认样式上**时间**和**datetime2**数据类型始终是 121。 如果您的查询依赖旧行为，请使用低于 110 的兼容性级别或在受影响的查询中显式指定 0 样式。<br /><br /> 将数据库升级到兼容性级别 110 将不更改已存储到磁盘的用户数据。 您必须相应手动更正此数据。 例如，如果您使用了 SELECT INTO 来从包含上述计算列表达式的源创建表，将存储数据（使用样式 0）而非存储计算列定义本身。 您需要手动更新此数据，以匹配样式 121。|  
|类型的远程表中的任何列**smalldatetime**分区视图中，引用将映射为**datetime**。 （在选择列表中的相同的序号位置） 的本地表中的相应列的类型必须为**datetime**。|类型的远程表中的任何列**smalldatetime**分区视图中，引用将映射为**smalldatetime**。 （在选择列表中的相同的序号位置） 的本地表中的相应列的类型必须为**smalldatetime**。<br /><br /> 在升级到 110 后，分布式分区视图将由于数据类型不匹配而失败。 你可以解决此问题通过到远程表上的数据类型更改**datetime**或设置兼容性级别为 100 的本地数据库或更低。|  
|SOUNDEX 函数实现以下规则：<br /><br /> 分隔两个具有相同数量的 SOUNDEX 代码中的辅音字母时，将忽略 1） 大写 H 或大写 W。<br /><br /> 2） 如果的前 2 个字符*character_expression* SOUNDEX 代码中具有相同数量，这两个字符包括在内。 如果一组并行辅音具有相同的 SOUNDEX 代码，则将不包含它们，第一个辅音除外。|SOUNDEX 函数实现以下规则：<br /><br /> 1） 如果大写 H 或大写 W 分隔两个在 SOUNDEX 代码中，右侧辅音具有相同数量的辅音字母将被忽略<br /><br /> 2） 如果并排显示的辅音字母一组具有相同数目的 SOUNDEX 代码中，所有这些均排除除第一个。<br /><br /> <br /><br /> 其他规则可能导致由 SOUNDEX 函数计算的值不同于在更低数据库兼容性级别时计算的值。 在升级到兼容性级别 110 后，可能需要重新生成使用 SOUNDEX 函数的索引、堆或 CHECK 约束。 有关详细信息，请参阅[SOUNDEX &#40;Transact SQL &#41;](../../t-sql/functions/soundex-transact-sql.md)|  
  
## <a name="differences-between-compatibility-level-90-and-level-100"></a>兼容性级别 90 和兼容性级别 100 之间的差异  
 本节介绍随兼容性级别 100 引入的新行为。  
  
|兼容性级别设置为 90|兼容性级别设置为 100|影响的可能性|  
|----------------------------------------|-----------------------------------------|---------------------------|  
|对于多语句表值函数，在创建它们时，无论会话级别设置如何，QUOTED_IDENTIFER 设置始终为 ON。|在创建多语句表值函数时，会遵循 QUOTED IDENTIFIER 会话设置。|Medium|  
|在创建或更改分区函数时**datetime**和**smalldatetime**函数中的文本将计算假设 US_English 的语言设置。|当前语言设置用于评估**datetime**和**smalldatetime**分区函数中的文本。|Medium|  
|INSERT 和 SELECT INTO 语句中允许使用（但会忽略）FOR BROWSE 子句。|INSERT 和 SELECT INTO 语句中不允许使用 FOR BROWSE 子句。|Medium|  
|OUTPUT 子句中允许使用全文谓词。|OUTPUT 子句中不允许使用全文谓词。|Low|  
|不支持 CREATE FULLTEXT STOPLIST、ALTER FULLTEXT STOPLIST 和 DROP FULLTEXT STOPLIST。 系统非索引字表自动与新的全文检索相关联。|支持 CREATE FULLTEXT STOPLIST、ALTER FULLTEXT STOPLIST 和 DROP FULLTEXT STOPLIST。|Low|  
|MERGE 不作为保留关键字强制应用。|MERGE 是完全保留的关键字。 在 100 和 90 兼容性级别下，都支持 MERGE 语句。|Low|  
|使用\<dml_table_source > INSERT 语句的自变量引发的语法错误。|您可以捕获嵌套的 INSERT、UPDATE、DELETE 或 MERGE 语句中 OUTPUT 子句的结果，然后将这些结果插入目标表或视图。 这是使用\<dml_table_source > INSERT 语句的自变量。|Low|
|除非指定 NOINDEX，否则 DBCC CHECKDB 或 DBCC CHECKTABLE 将对单个表或索引视图及其所有非聚集索引和 XML 索引同时执行物理和逻辑一致性检查。 不支持空间索引。|除非指定 NOINDEX，否则 DBCC CHECKDB 或 DBCC CHECKTABLE 将对单个表及其所有非聚集索引同时执行物理和逻辑一致性检查。 但是，在默认情况下，仅对 XML 索引、空间索引和索引视图执行物理一致性检查。<br /><br /> 如果指定了 WITH EXTENDED_LOGICAL_CHECKS，则将对索引视图、XML 索引和空间索引（如果存在）执行逻辑检查。 默认情况下，先执行物理一致性检查，然后执行逻辑一致性检查。 如果还指定了 NOINDEX，则仅执行逻辑检查。|Low|  
|如果将 OUTPUT 子句和数据操作语言 (DML) 语句一起使用，并且在语句执行过程中发生运行时错误，则会终止并回滚整个事务。|如果将 OUTPUT 子句和数据操作语言 (DML) 语句一起使用，并且在语句执行过程中发生运行时错误，则行为取决于 SET XACT_ABORT 设置。 如果 SET XACT_ABORT 设置为 OFF，则由使用 OUTPUT 子句的 DML 语句所生成的语句中止错误将终止该语句，但批处理的执行仍会继续，并且不会回滚事务。 如果 SET XACT_ABORT 设置为 ON，则由使用 OUTPUT 子句的 DML 语句所生成的全部运行时错误都将终止批处理，并回滚事务。|Low|  
|CUBE 和 ROLLUP 不作为保留关键字强制应用。|CUBE 和 ROLLUP 是 GROUP BY 子句中的保留关键字。|Low|  
|严格验证应用到的 XML 元素**anyType**类型。|宽松验证应用到的元素**anyType**类型。 有关详细信息，请参阅[通配符组成部分和内容验证](../../relational-databases/xml/wildcard-components-and-content-validation.md)。|Low|  
|特殊属性**xsi: nil**和**xsi: type**无法查询或修改的数据操作语言语句。<br /><br /> 这意味着，`/e/@xsi:nil`失败时`/e/@*`忽略**xsi: nil**和**xsi: type**属性。 但是，`/e`返回**xsi: nil**和**xsi: type**属性的一致性`SELECT xmlCol`，即使`xsi:nil = "false"`。|特殊属性**xsi: nil**和**xsi: type**作为正则属性存储，并可以查询和修改。<br /><br /> 例如，执行查询`SELECT x.query('a/b/@*')`返回所有属性，包括**xsi: nil**和**xsi: type**。 若要排除这些类型在查询中的，替换`@*`与`@*[namespace-uri(.) != "`*插入 xsi 命名空间 uri* `"`和 not`(local-name(.) = "type"`或`local-name(.) ="nil".`|Low|  
|用于将 XML 常量字符串值转换为 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] datetime 类型的用户定义函数被标记为确定的。|用于将 XML 常量字符串值转换为 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] datetime 类型的用户定义函数被标记为不确定的。|Low|  
|不完全支持 XML 联合和列表类型。|完全支持联合和列表类型，包括以下功能：<br /><br /> 列表的联合<br /><br /> 联合的联合<br /><br /> 原子类型的列表<br /><br /> 联合的列表|低|  
|当视图或内联表值函数中包含 xQuery 方法时，不对该方法所需的 SET 选项进行验证。|当视图或内联表值函数中包含 xQuery 方法时，对该方法所需的 SET 选项进行验证。 如果该方法的 SET 选项设置不正确，将引发一个错误。|Low|  
|包含行尾字符（回车符和换行符）的 XML 属性值不根据 XML 标准进行规范化。 即返回回车符和换行符，而不是单个换行符。|包含行尾字符（回车符和换行符）的 XML 属性值会根据 XML 标准进行规范化。 也就是说，外部已分析实体（包括文档实体）中的所有换行符都会在输入时进行规范化，方法是将两字符序列 #xD #xA 和后面没有跟 #xA 的所有 #xD 都转换为单个 #xA 字符。<br /><br /> 使用属性来传输包含行尾字符的字符串值的应用程序接收到的这些字符将和提交时有所不同。 若要避免规范化过程，请使用 XML 数字字符实体对所有行尾字符进行编码。|Low|  
|ROWGUIDCOL 和 IDENTITY 列属性可能错误地命名为约束。 例如，`CREATE TABLE T (C1 int CONSTRAINT MyConstraint IDENTITY)` 语句可以执行，但约束名不会保留，也无法让用户访问。|ROWGUIDCOL 和 IDENTITY 列属性不能命名为约束。 返回错误 156。|Low|  
|使用双向赋值（如 `UPDATE T1 SET @v = column_name = <expression>`）来更新列会产生意外后果，因为在语句执行过程中，可以在其他子句（如 WHERE 和 ON 子句）中使用变量的实时值，而不是使用语句起始值。 这会导致谓词的含义无法预测地逐行变化。<br /><br /> 只有在兼容性级别设置为 90 时，此行为才适用。|使用双向赋值来更新列会产生预期的结果，因为在语句执行过程中，只会访问列的语句起始值。|Low|  
|请参阅下面的示例部分中的示例 E。|请参阅下面的示例部分中的示例 F。|Low|  
|ODBC 函数 {fn CONVERT()} 使用语言的默认日期格式。 对于有些语言，默认格式为 YDM，这会导致在将 CONVERT() 与要求使用 YMD 格式的其他函数（如 {fn CURDATE()}）结合使用时出现转换错误。|在转换为 ODBC 数据类型 SQL_TIMESTAMP、SQL_DATE、SQL_TIME、SQLDATE、SQL_TYPE_TIME 和 SQL_TYPE_TIMESTAMP 时，ODBC 函数 {fn CONVERT()} 使用样式 121（一种独立于语言的 YMD 格式）。|Low|  
|日期时间内部函数（如 DATEPART）不需要字符串输入值，即可成为有效的日期时间文字。 例如，SELECT DATEPART (year, '2007/05-30') 可以成功编译。|日期时间内部函数（如 DATEPART）需要字符串输入值，才能成为有效的日期时间文字。 在使用无效的日期时间文字时，会返回错误 241。|Low|  
  
## <a name="reserved-keywords"></a>保留关键字  
 兼容性设置还确定了[!INCLUDE[ssDE](../../includes/ssde-md.md)]所保留的关键字。 下表显示了每个兼容性级别所引入的保留关键字。  
  
|兼容性级别设置|保留关键字|  
|----------------------------------|-----------------------|  
|130|待定。|  
|120|无。|  
|110|WITHIN GROUP、TRY_CONVERT、SEMANTICKEYPHRASETABLE、SEMANTICSIMILARITYDETAILSTABLE、SEMANTICSIMILARITYTABLE|  
|100|CUBE、MERGE、ROLLUP|  
|90|EXTERNAL、PIVOT、UNPIVOT、REVERT、TABLESAMPLE|  
  
 在给定兼容性级别，保留关键字包括在该级别或较低级别引入的所有关键字。 例如，对于兼容性级别为 110 的应用程序，将保留上表列出的所有关键字。 在较低的兼容性级别中，级别 100 的关键字仍保留有效的对象名，但与这些关键字相对应的级别 110 的语言功能将不可用。  
  
 一旦引入，关键字便会保持为保留关键字。 例如，在兼容性级别 90 中引入的保留关键字 PIVOT 在级别 100、110 和 120 中也被保留。  
  
 如果某一应用程序使用对其保留级别而言是关键字的标识符，则该应用程序将失败。 若要解决此问题，请将任一括号之间的标识符 (**[]**) 或引号 (**""**); 例如，若要升级的应用程序使用的标识符**外部**到兼容级别 90，则可以更改为标识符**[外部]**或**"EXTERNAL"**。  
  
 有关详细信息，请参阅[保留关键字 (Transact-SQL) ](../../t-sql/language-elements/reserved-keywords-transact-sql.md)。  
  
## <a name="permissions"></a>Permissions  
 需要对数据库拥有 ALTER 权限。  
  
## <a name="examples"></a>示例  
  
### <a name="a-changing-the-compatibility-level"></a>A. 更改兼容性级别  
 下面的示例更改的兼容级别[!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]数据库到`110,` [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]。  
  
```tsql  
ALTER DATABASE AdventureWorks2012  
SET COMPATIBILITY_LEVEL = 110;  
GO  
```  
  
 下面的示例返回当前数据库的兼容性级别。  
  
```tsql  
SELECT name, compatibility_level   
FROM sys.databases   
WHERE name = db_name();  
```  
  
### <a name="b-ignoring--the-set-language-statement-except-under-compatibility-level-120"></a>B. 忽略除兼容性级别 120 下的 SET LANGUAGE 语句  
 以下查询将忽略除兼容性级别 120 下的 SET LANGUAGE 语句。  
  
```tsql  
SET DATEFORMAT dmy;   
DECLARE @t2 date = '12/5/2011' ;  
SET LANGUAGE dutch;   
SELECT CONVERT(varchar(11), @t2, 106);   
  
-- Results when the compatibility level is less than 120.   
12 May 2011   
  
-- Results when the compatibility level is set to 120).  
12 mei 2011  
```  
  
### <a name="c"></a>C.  
 对于兼容级别设置为 110 或更低，EXCEPT 子句右侧的递归引用创建无限循环。  
  
```tsql  
WITH   
cte AS (SELECT * FROM (VALUES (1),(2),(3)) v (a)),  
r   
AS (SELECT a FROM Table1  
UNION ALL  
(SELECT a FROM Table1 EXCEPT SELECT a FROM r) )   
SELECT a   
FROM r;  
  
```  
  
### <a name="d"></a>D.  
 此示例显示样式 0 和 121 之间的差异。 有关日期和时间的样式的详细信息，请参阅[CAST 和 CONVERT &#40;Transact SQL &#41;](../../t-sql/functions/cast-and-convert-transact-sql.md).  
  
```tsql  
CREATE TABLE t1 (c1 time(7), c2 datetime2);   
  
INSERT t1 (c1,c2) VALUES (GETDATE(), GETDATE());  
  
SELECT CONVERT(nvarchar(16),c1,0) AS TimeStyle0  
       ,CONVERT(nvarchar(16),c1,121)AS TimeStyle121  
       ,CONVERT(nvarchar(32),c2,0) AS Datetime2Style0  
       ,CONVERT(nvarchar(32),c2,121)AS Datetime2Style121  
FROM t1;  
  
-- Returns values such as the following.  
TimeStyle0       TimeStyle121       
Datetime2Style0      Datetime2Style121  
---------------- ----------------   
-------------------- --------------------------  
3:15PM           15:15:35.8100000   
Jun  7 2011  3:15PM  2011-06-07 15:15:35.8130000  
```  
  
### <a name="e"></a>E.  
 在包含顶级 UNION 运算符的语句中，允许使用变量赋值，但会返回意外的结果。 例如，在以下语句中，将来自两个表的联合的 `@v` 列的值赋给局部变量 `BusinessEntityID`。 按照定义，如果 SELECT 语句返回多个值，则将返回的最后一个值赋给变量。 在这种情况下，会正确地将最后一个值赋给变量，但还会返回 SELECT UNION 语句的结果集。  
  
```tsql  
ALTER DATABASE AdventureWorks2012  
SET compatibility_level = 90;  
GO  
USE AdventureWorks2012;  
GO  
DECLARE @v int;  
SELECT @v = BusinessEntityID FROM HumanResources.Employee  
UNION ALL  
SELECT @v = BusinessEntityID FROM HumanResources.EmployeeAddress;  
SELECT @v;  
```  
  
### <a name="f"></a>F.  
 在包含顶级 UNION 运算符的语句中不允许变量赋值。 返回错误 10734。 若要纠正该错误，请重写查询，如下例所示。  
  
```tsql  
DECLARE @v int;  
SELECT @v = BusinessEntityID FROM   
    (SELECT BusinessEntityID FROM HumanResources.Employee  
     UNION ALL  
     SELECT BusinessEntityID FROM HumanResources.EmployeeAddress) AS Test;  
SELECT @v;  
```  
  
## <a name="see-also"></a>另请参阅  
 [ALTER DATABASE (Transact-SQL)](../../t-sql/statements/alter-database-transact-sql.md)   
 [保留关键字 (Transact-SQL)](../../t-sql/language-elements/reserved-keywords-transact-sql.md)   
 [CREATE DATABASE (SQL Server Transact-SQL)](../../t-sql/statements/create-database-sql-server-transact-sql.md)   
 [DATABASEPROPERTYEX (Transact-SQL)](../../t-sql/functions/databasepropertyex-transact-sql.md)   
 [sys.databases (Transact-SQL)](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md)   
 [sys.database_files (Transact-SQL)](../../relational-databases/system-catalog-views/sys-database-files-transact-sql.md)  
  
  
