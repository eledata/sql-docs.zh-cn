---
title: "数据查看器 | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: data-flow
ms.reviewer: 
ms.suite: sql
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.dts.designer.dataviewer.f1
helpviewer_keywords:
- Data Viewer dialog box
ms.assetid: 6351309a-688f-4e82-9697-1712130f10a1
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: f9541c6d49a6fc4f7a0dea8becdb4022ff53e3f6
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2018
---
# <a name="data-viewer"></a>数据查看器
  如果将路径配置为使用数据查看器，当数据在两个数据流组件之间移动时，数据查看器将依次显示各个缓冲区的数据。  
  
## <a name="options"></a>“常规”  
 **绿色箭头**  
 单击此项可显示下一个缓冲区中的数据。 如果数据可以在单个缓冲区中移动，此选项将不可用。  
  
 **分离**  
 分离数据查看器。  
  
 **注意** 分离数据查看器并不会删除数据查看器。 在分离数据查看器后，数据可继续通过路径流动，但查看器中的数据将不会更新以匹配每个缓冲区中的数据。  
  
 **附加**  
 附加数据查看器。  
  
 **注意** 数据查看器在附加后会显示数据流的每个缓冲区中的信息，然后暂停。 您可以通过使用绿色箭头依次显示各缓冲区的信息。  
  
 **复制数据**  
 将当前缓冲区中的数据复制到剪贴板。  
  
## <a name="see-also"></a>另请参阅  
 [调试数据流](../../integration-services/troubleshooting/debugging-data-flow.md)  
  
  
