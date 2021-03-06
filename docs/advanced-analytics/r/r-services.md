---
title: "Microsoft 机器学习服务 |Microsoft 文档"
ms.date: 11/09/2017
ms.reviewer: 
ms.suite: sql
ms.prod: machine-learning-services
ms.prod_service: machine-learning-services
ms.component: r
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 341e80f5-3b59-4122-bbaa-969d7904297d
caps.latest.revision: 
author: jeannt
ms.author: jeannt
manager: cgronlund
ms.workload: On Demand
ms.openlocfilehash: 40c76cba27559c8fcc314ce4c9761ee42edacac0
ms.sourcegitcommit: 657d18fc805512c9574b2fe7451310601b9d78cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
---
# <a name="microsoft-machine-learning-services"></a>Microsoft 机器学习服务
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

Microsoft 机学习服务旨在提供一个可扩展、 可缩放平台，使用机器学习服务的应用程序集成机器学习任务和工具。 平台必须提供所有用户的需求所涉及的数据开发和分析过程中，从数据科学家给架构师和数据库管理员。

主要优点包括：

+ 可缩放的分析
+ 多个平台和计算上下文，"一次的代码，到处部署"的解决方案
+ 通过将分析数据，从而避免数据移动和数据的风险
+ 数据科研人员可以选择自己的工具和语言
+ 与 Microsoft 的企业功能集成开放源代码的最佳的功能
+ 简化的管理
+ 轻松部署和使用预测模型

## <a name="in-database-analytics-with-sql-server"></a>与 SQL Server 数据库中分析

在 SQL Server 2016 中，Microsoft 将启动两个服务器平台将受欢迎的开源 R 语言与业务应用程序相集成：

+ **集成的**SQL Server R Services（数据库内） [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]
+ **Microsoft R Server**，对于 Windows 和 Linux 服务器上的企业级 R 部署

在 SQL Server 自 2017 年 1，名称已更改以反映的常用 Python 语言的支持。

+ **SQL Server 计算机学习 Services （数据库）**支持的数据库中分析的 R 和 Python。
+ **Microsoft 机器学习 Server**在 Windows、 Linux 和 HDInsight Spark 和 Hadoop 群集上支持 R 和 Python 的部署。

### <a name="benefits"></a>优势

通过允许在数据库所在的计算机上运行的 R，Microsoft 机器学习服务将计算融入到数据。 它包括外运行的快速启动板服务[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]处理并与 R 或 Python 运行时的安全地进行通信。

使用 SQL Server 计算机学习 Services，可以训练模型、 生成图形，执行评分，并安全地移动数据之间[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]和 R 或 Python。

负责测试和开发解决方案的数据科学家可以从远程开发计算机发送脚本，并在服务器上运行其代码，而无需移动数据。 开发人员可以通过 SQL 存储过程中嵌入机器学习代码到 SQL Server 部署已完成的解决方案。

安装 SQL Server 的机器学习时，你获得的开放源代码 R 或 Python 语言，以及由 Microsoft 提供的可缩放 R 和 Python 库的分布。 SQL Server 数据库引擎还包括新组件设计为可以巩固理解连接，并确保更快、 更安全的通信，与 R 或 Python 等外部语言。

### <a name="where-to-get-it"></a>获取它的位置

若要开始，请参阅以下资源：

+ [SQL Server R Services](sql-server-r-services.md)
+ [SQL Server Python Services](../python/sql-server-python-services.md)
+ [机器学习教程](../tutorials/machine-learning-services-tutorials.md)

> [!NOTE]
> 仅在 SQL Server 自 2017 年中提供的 Python 的支持。 

## <a name="machine-learning-server-standalone-and-microsoft-r-server-standalone"></a>机器学习 Server （独立） 和 Microsoft R Server （独立）

此独立服务器系统支持在多个平台和使用多个企业数据源，如 Linux 和 HDInsight 上的分布式、 可缩放 R 解决方案。 如果你不需要与 SQL Server 进行集成，你可以安装 R Server 以启用快速开发、 部署和操作化的机器学习解决方案。 你还可以使用 R Server 安装程序升级与 SQL Server 实例关联的 R 组件，获取最新版本的。

如果你安装 Microsoft 机器学习服务器使用 SQL Server 2017 安装程序，你可以部署和使用 Python 应用程序。

有关详细信息，请参阅[Microsoft 机器学习 Server](https://docs.microsoft.com/r-server/index)。

## <a name="related-technologies"></a>相关的技术

Microsoft 提供广泛支持用于机器学习生态系统，包括工具、 提供程序、 增强的 R 和 Python 包、 云开发和服务平台和集成的开发环境。

### <a name="r-tools-for-visual-studio"></a>用于 Visual Studio 的 R 工具

Visual Studio 为 R 语言提供完整的开发环境。 该插件包含编辑器、交互式窗口、绘图、调试器等等。 你可以通过 R.NET 和 rClr 等开放源代码库从 R 使用 .NET 语言或从 .NET 调用 R。

Visual Studio 还具有很好的 Python 开发环境。 没有任何更方便的方法，以同时继续享受访问 SQL 数据库开发工具使用机器学习语言。

有关详细信息，请参阅：

+ [用于 Visual Studio 的 R 工具](https://www.visualstudio.com/vs/rtvs/)
+ [Python-Visual Studio](https://www.visualstudio.com/vs/python/)

### <a name="azure-machine-learning"></a>Azure 机器学习

当你在 Azure Machine Learning Studio 中创建自己的工作区时，你有权访问超过 400 个预加载的 R 包。 你还可以选择创建一个试验，R，用于部署 R 使用标准 CRAN R 分布中，或 Microsoft R Open 时。 甚至可以创建你自己的 R 包，并将其上载到 Azure 以作为自定义模块运行。

许多 Azure ML 中提供的算法现在包括在 Microsoft 机器学习服务中，作为 MicrosoftML 包的一部分。 有关详细信息，请参阅[MicrosoftML](https://docs.microsoft.com/r-server/r-reference/microsoftml/microsoftml-package)。

Azure 机器学习是另一个方便的平台，用于数据科学家和开发人员需要生成、 训练，并部署使用 Web 服务模型。 你可以将解决方案发布到[机器学习应用商店](http://datamarket.azure.com/browse/data?category=machine-learning)。

有关在 Azure 机器学习服务中，令人兴奋更改详细信息以支持专业人员的数据科学家，请参阅以下资源：

+ [什么是 Azure 机器学习？](https://docs.microsoft.com/azure/machine-learning/preview/overview-what-is-azure-ml)
+ [模型管理功能](https://docs.microsoft.com/azure/machine-learning/preview/model-management-overview)

### <a name="data-science-virtual-machines"></a>数据科学虚拟机

用户可以在 Microsoft Azure 中部署 [!INCLUDE[rsql_platform](../../includes/rsql-platform-md.md)] 的预安装和预配置版本，这样就可以立即在云上轻松地开始使用数据浏览和建模，而无需在本地设置完整配置的系统。

Azure 应用商店包含支持数据科学的多个虚拟机。

+ **Microsoft 数据科学虚拟机**使用机器学习服务器配置为以及 Python （Anaconda 分发）、 Jupyter 笔记本 server、 Visual Studio Community Edition，Power BI Desktop、 Azure SDK 和 SQL服务器。

    新[数据科学 VM 的 Windows Server 2016](http://aka.ms/dsvm/win2016)提供了常用深度学习框架，例如 CNTK GPU 版本。 预安装的工具包括 GPU NVIDIA 驱动程序、 CUDA 工具包 8.0 和 GPU 工作负荷的 NVIDIA cuDNN 库。 只需几分钟，您就可以有一个完整的环境，以便生成可以在 CPU 或 CPU 和 GPU 运行的深度学习模型。

+ 对于 R Server 或机器学习服务器，我们建议 Microsoft 机器学习服务器 2017 Linux 或 Windows 2016 服务器。

+ 若要获取与 SQL Server 机器学习的 Azure 映像，我们建议任何包含的虚拟机产品/服务**SQL Server 2017**。 时选择的映像，请遵循有关层和服务级别，其他建议，以确保 VM 可以支持机器学习工作负荷。

## <a name="next-steps"></a>后续步骤

[机器学习服务入门](getting-started-with-sql-server-r-services.md)

[机器学习 Server 入门](getting-started-with-microsoft-r-server-standalone.md)

[安装 SQL Server 数据库引擎](../../database-engine/install-windows/install-sql-server-database-engine.md)
