---
title: 删除挖掘模型 (DMX) |Microsoft 文档
ms.custom: ''
ms.date: 03/02/2016
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: data-mining
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- DROP_MINING_MODEL
dev_langs:
- DMX
helpviewer_keywords:
- DROP MINING MODEL statement
- deleting mining models
- removing mining models
- dropping mining models
- mining models [Analysis Services], deleting
ms.assetid: 8ff561d0-a526-4712-9fff-11df9f8c45a1
caps.latest.revision: 33
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: 363b3e52463f2c9e58a3f31895e4a685a28761c6
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="drop-mining-model-dmx"></a>DROP MINING MODEL (DMX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  从数据库中删除挖掘模型。  
  
## <a name="syntax"></a>语法  
  
```  
  
DROP MINING MODEL <model >  
```  
  
## <a name="arguments"></a>参数  
 *model*  
 一个模型标识符。  
  
## <a name="examples"></a>示例  
 下面的示例代码会删除挖掘模型 NBSample。  
  
```  
DROP MINING MODEL [NBSample]  
```  
  
## <a name="see-also"></a>另请参阅  
 [数据挖掘扩展插件 &#40; DMX &#41;数据定义语句](../dmx/dmx-statements-data-definition.md)   
 [数据挖掘扩展插件 &#40; DMX &#41;数据操作语句](../dmx/dmx-statements-data-manipulation.md)   
 [数据挖掘扩展插件 (DMX) 语句引用](../dmx/data-mining-extensions-dmx-statements.md)  
  
  
