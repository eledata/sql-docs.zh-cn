---
title: "命令在表格模型脚本语言 (TMSL) |Microsoft 文档"
ms.date: 05/30/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.custom: 
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4eb07192-6f53-4426-830a-d63a945dbcab
caps.latest.revision: "12"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 39959a86e064da782097ddc75d9d3651b4d436fa
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="tmsl-reference---commands"></a>TMSL 参考-命令
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]你可以执行命令 XMLA 终结点上, 构建 JSON 使用表格模型脚本语言 (TMSL)，对表格模型数据库中的对象定义。   请参阅[对象定义中表格模型脚本语言 &#40;TMSL &#41;](../../analysis-services/tabular-models-scripting-language-objects/tmsl-reference-tabular-objects.md)有关使用以下命令使用的对象的列表。  
  
## <a name="object-operations"></a>对象操作  
  
|||  
|-|-|  
|[Alter 命令 &#40;TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/alter-command-tmsl.md)|内联对进行修改的对象而无需指定完整定义。|  
|[创建命令 &#40;TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/create-command-tmsl.md)|创建一个新的对象，包括其后代。|  
|[CreateOrReplace 命令 &#40;TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/createorreplace-command-tmsl.md)|创建或替换的对象定义的部分。 必须提供完整定义。|  
|[删除命令 &#40;TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/delete-command-tmsl.md)|删除对象，包括其后代。|  
  
## <a name="data-refresh-operations"></a>数据刷新操作  
  
|||  
|-|-|  
|[撰写 MergePartitions 命令 &#40;TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/mergepartitions-command-tmsl.md)|将目标分区合并到一个源，并删除目标。|  
|[刷新命令 &#40;TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/refresh-command-tmsl.md)|处理数据库、 表或分区。|  
  
## <a name="scripting"></a>脚本编写  
  
|||  
|-|-|  
|[Sequence 命令 &#40;TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/sequence-command-tmsl.md)|按顺序或并行批处理操作|  
  
## <a name="database-management-operations"></a>数据库管理操作  
  
|||  
|-|-|  
|[附加命令 &#40;TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/attach-command-tmsl.md)|将文件添加到服务器。|  
|[分离命令 &#40;TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/detach-command-tmsl.md)|从服务器中删除文件。|  
|[备份命令 &#40;TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/backup-command-tmsl.md)|创建数据库的备份文件。|  
|[还原命令 &#40;TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/restore-command-tmsl.md)|将数据库还原到服务器。|  
|[同步命令 &#40;TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/synchronize-command-tmsl.md)|利用另一个现有数据库同步 Analysis Services 数据库。|  
  
## <a name="see-also"></a>另请参阅  
 [表格模型脚本语言 (TMSL) 参考](../../analysis-services/tabular-model-scripting-language-tmsl-reference.md)   
 [安装 Analysis Services 数据提供程序 &#40;AMO、 ADOMD.NET、 MSOLAP 和 #41;](../../analysis-services/instances/install-windows/install-analysis-services-data-providers-amo-adomd-net-msolap.md)   
 [Analysis Services 中表格模型的兼容级别](../../analysis-services/tabular-models/compatibility-level-for-tabular-models-in-analysis-services.md)  
  
  
