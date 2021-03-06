---
title: "XML for Analysis 遵从性 (XMLA) |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to: SQL Server 2016 Preview
helpviewer_keywords:
- compliance [XML for Analysis]
- XML for Analysis, compliance
- XMLA, extended functionality
- XML for Analysis, extended functionality
- XMLA, compliance
- extending XML for Analysis
ms.assetid: d987d320-5581-4454-ad45-68e3a22175b6
caps.latest.revision: "15"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: efd2d4cfd7adb6185abdd383a261494495817ec5
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="xml-for-analysis-compliance-xmla"></a>XML for Analysis 遵从性 (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]XML for Analysis 1.1 规范介绍在万维网支持对驻留的数据源的数据访问的开放标准。 本主题详细介绍与支持的 XML for Analysis 1.1 规范的符合度[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]。  
  
## <a name="compliant-items"></a>符合项  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 符合 XML for Analysis 1.1 规范中列出的所有必须遵循的内容。 此外，[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 还实现了 XML for Analysis 1.1 规范中描述的下列可选项。  
  
|项|规范|实现|  
|----------|-------------------|--------------------|  
|会话支持|在 XML for Analysis 1.1 规范的“Support for Statefulness in XML for Analysis”（XML for Analysis 中的有状态性支持）部分列出的 SOAP 标头元素。|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 以规范所述方式，支持所有列出的 SOAP 标头元素。|  
  
## <a name="extensions"></a>扩展项  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 还扩展了 XML for Analysis 1.1 规范，以支持下列附加特性和功能。  
  
|项|规范|实现|  
|----------|-------------------|--------------------|  
|协议协商|XML for Analysis 1.1 规范中不包含相关信息|通过添加 ProtocolCapabilities 标头元素[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]以支持的协议功能协商。|  
|Discover 方法支持的 XML for Analysis (XMLA) 命令|XML for Analysis 1.1 规范支持下列命令：<br /><br /> [语句元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/statement-element-xmla.md)|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 支持下列命令：<br /><br /> [Alter 元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/alter-element-xmla.md)<br /><br /> [Backup 元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/backup-element-xmla.md)<br /><br /> [Batch 元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/batch-element-xmla.md)<br /><br /> [BeginTransaction 元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/begintransaction-element-xmla.md)<br /><br /> [取消元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/cancel-element-xmla.md)<br /><br /> [ClearCache 元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/clearcache-element-xmla.md)<br /><br /> [CommitTransaction 元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/committransaction-element-xmla.md)<br /><br /> [创建元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/create-element-xmla.md)<br /><br /> [删除元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/delete-element-xmla.md)<br /><br /> [DesignAggregations 元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/designaggregations-element-xmla.md)<br /><br /> [删除元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/drop-element-xmla.md)<br /><br /> [插入元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/insert-element-xmla.md)<br /><br /> [锁定元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/lock-element-xmla.md)<br /><br /> [撰写 MergePartitions 元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/mergepartitions-element-xmla.md)<br /><br /> [NotifyTableChange 元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/notifytablechange-element-xmla.md)<br /><br /> [Process 元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/process-element-xmla.md)<br /><br /> [还原元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/restore-element-xmla.md)<br /><br /> [RollbackTransaction 元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/rollbacktransaction-element-xmla.md)<br /><br /> [语句元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/statement-element-xmla.md)<br /><br /> [订阅元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/subscribe-element-xmla.md)<br /><br /> [同步元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/synchronize-element-xmla.md)<br /><br /> [解锁元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/unlock-element-xmla.md)<br /><br /> [更新元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/update-element-xmla.md)<br /><br /> [UpdateCells 元素 &#40;XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/updatecells-element-xmla.md)|  
|表格行集中的列错误|未在 XML for Analysis 1.1 规范中列出。|[错误](../../analysis-services/xmla/xml-elements-properties/error-element-xmla.md)元素由[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]列元素中包含的报告错误[行](../../analysis-services/xmla/xml-elements-properties/error-element-xmla.md)元素。|  
  
## <a name="see-also"></a>另请参阅  
 [XML for Analysis (XMLA) 参考](../../analysis-services/xmla/xml-for-analysis-xmla-reference.md)  
  
  
