---
title: "Microsoft 基于 COM 的冲突解决程序 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM-based resolvers [SQL Server replication]
- custom resolvers [SQL Server replication]
ms.assetid: a6637e4b-4e6b-40aa-bee6-39d98cc507c8
caps.latest.revision: 38
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: b0389bb0387489b581aae3225fd1a02e7bc9d713
ms.contentlocale: zh-cn
ms.lasthandoff: 06/22/2017

---
# <a name="advanced-merge-replication-conflict---com-based-resolvers"></a>高级合并复制冲突 - 基于 COM 的解决程序
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 附带的所有基于 COM 的解决程序都处理更新冲突，并且在得到指示时，它们还会处理插入和删除冲突。 所有冲突解决程序都能处理列跟踪，大多数还能处理行跟踪。 这些冲突解决程序及所有其他基于 COM 的冲突解决程序都声明它们能处理的冲突类型，而合并复制代理使用默认的冲突解决程序处理所有其他冲突类型。  
  
 冲突解决程序在安装 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]时安装。 可执行存储过程 **sp_enumcustomresolvers** 查看计算机上注册的所有冲突解决程序。 执行此过程将在一个单独的结果集中显示每个冲突解决程序的说明和全局唯一标识符 (GUID)。  
  
 若要指定冲突解决程序，请参阅 [Specify a Merge Article Resolver](../../../relational-databases/replication/publish/specify-a-merge-article-resolver.md)。  
  
 下表说明了特定冲突解决程序的属性。  
  
|名称|要求的输入|说明|注释|  
|----------|--------------------|-----------------|--------------|  
|[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Additive Conflict Resolver|要求和的列的名称。 它必须为算术数据类型（例如 **int**、 **smallint**、 **numeric**等）。|冲突解决入选方由优先级值确定。 指定列的值设置为源列值与目标列值之和。 如果其中一列设置为 NULL，则结果按另一列的值设置。|只支持更新冲突和列跟踪。|  
|[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Averaging Conflict Resolver|要平均化的列的名称。 它必须为算术数据类型（例如 **int**、 **smallint**、 **numeric**等）。|冲突解决入选方由优先级值确定。 所得列的值设置为源列值与目标列值的平均值。 如果其中一列设置为 NULL，则结果按另一列的值设置。|只支持更新冲突和列跟踪。|  
|[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] DATETIME (Earlier Wins) Conflict Resolver|用于确定冲突解决入选方的列的名称。 它必须为 **datetime** 数据类型。|具有较早的 **datetime** 值的列确定冲突解决入选方。 如果其中一列设置为 NULL，则包含另一列的行为入选方。|支持更新冲突、行和列跟踪。 列值直接进行比较，并且不对不同的时区进行比较。|  
|[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] DATETIME (Later Wins) Conflict Resolver|用于确定冲突解决入选方的列的名称。 它必须为 **datetime** 数据类型。|具有较晚的 **datetime** 值的列确定冲突解决入选方。 如果其中一列设置为 NULL，则包含另一列的行为入选方。|支持更新冲突、行和列跟踪。|  
|[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Maximum Conflict Resolver|用于确定冲突解决入选方的列的名称。 它必须为算术数据类型（例如 **int**、 **smallint**、 **numeric**等）。|具有较大数值的列确定冲突解决入选方。 如果其中一列设置为 NULL，则包含另一列的行为入选方。|支持行和列跟踪。|  
|[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Minimum Conflict Resolver|用于确定冲突解决入选方的列的名称。 它必须为算术数据类型（例如 **int**、 **smallint**、 **numeric**等）。|具有较小数值的列确定冲突解决入选方。 如果其中一列设置为 NULL，则包含另一列的行为入选方。|支持更新冲突、行和列跟踪。|  
|[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Merge Text Conflict Resolver|文本列的名称和分隔符，例如 `@resolver_info = '[col1][===]'`。|冲突解决入选方由优先级值确定。 冲突的文本列设置为合并值，该值的构成是：通用前缀，后面依次跟着发布服务器的特有部分、分隔符及订阅服务器的特有部分。|只支持更新冲突和列跟踪。|  
|[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscriber Always Wins Conflict Resolver|无输入。|订阅服务器无论是作为源服务器还是目的服务器，始终是入选方。|支持所有冲突类型。|  
|[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Priority Column Resolver|用于确定冲突解决入选方的列的名称。 它必须为算术数据类型（例如 **int**、 **smallint**、 **numeric**等）。|具有较大数值的列确定冲突解决入选方。 如果其中一列设置为 NULL，则包含另一列的行为入选方。|支持更新冲突、行和列跟踪。|  
|[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Upload Only Conflict Resolver|无输入。|接受上载到发布服务器的更改；但更改不下载到订阅服务器。|支持所有冲突类型。|  
|[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Download Only Conflict Resolver|无输入。|拒绝上载到发布服务器的更改；但更改下载到订阅服务器。|支持所有冲突类型。|  
|[!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQL Server 存储过程冲突解决程序|冲突解决程序为处理冲突应调用的存储过程的名称。|冲突解决取决于在存储过程中指定的逻辑。|支持更新冲突。 有关详细信息，请参阅[为合并项目实现自定义冲突解决程序](../../../relational-databases/replication/implement-a-custom-conflict-resolver-for-a-merge-article.md)|  
  
## <a name="see-also"></a>另请参阅  
 [Advanced Merge Replication Conflict Detection and Resolution](../../../relational-databases/replication/merge/advanced-merge-replication-conflict-detection-and-resolution.md)   
 [sp_enumcustomresolvers (Transact-SQL)](../../../relational-databases/system-stored-procedures/sp-enumcustomresolvers-transact-sql.md)  
  
  