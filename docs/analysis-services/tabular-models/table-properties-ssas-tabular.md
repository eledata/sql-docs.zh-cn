---
title: "表属性 |Microsoft 文档"
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: 
ms.component: data-mining
ms.reviewer: 
ms.suite: pro-bi
ms.custom: 
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.asvs.bidtoolset.tableprop.f1
ms.assetid: 16d3347b-7e43-4a6b-9956-fdd6ede092e6
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 202902448a31fda27ab2c4d8c0bc894cc50da3db
ms.sourcegitcommit: d8ab09ad99e9ec30875076acee2ed303d61049b7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2018
---
# <a name="table-properties"></a>Table Properties 
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
本文介绍表格模型表属性。 此处所述的属性不同于“编辑表属性”对话框中的那些属性，后者可以定义从源导入哪些列。  
  
 本主题的内容：  
  
-   [表的属性](#bkmk_properties)  
  
-   [配置表属性设置](#bkmk_config_prop)  
  
##  <a name="bkmk_properties"></a> 表的属性  
 **基本**  
  
|属性|默认设置|Description|  
|--------------|---------------------|-----------------|  
|**连接名称**|\<连接名称 >|与表的数据源的连接名称。<br /><br /> 若要编辑连接，请单击该按钮。|  
|**Hidden**|False|指定是否在报表客户端字段列表中隐藏表。|  
|**分区**||表的分区不能显示在 **“属性”** 窗口中。 若要查看、创建或编辑分区，请单击该按钮以打开分区管理器。|  
|**源数据**||表的源数据不能显示在 **“属性”** 窗口中。 若要查看或编辑源数据，请单击该按钮以打开“编辑表属性”对话框。|  
|**表说明**||表的文本说明。<br /><br /> 在 [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)]中，如果最终用户将光标置于字段列表的此表上方，则说明将以工具提示的形式出现。|  
|**表名**|\<友好名称 >|指定表的友好名称。 当您使用“表导入向导”导入表时或在导入后的任意时间，可以指定表名。 模型中的表名可以不同于源的相关表名。 表的友好名称显示在报表客户端应用程序的字段列表以及 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]的模型数据库中。|  
  
 **报表属性**  
  
 有关详细的说明和用于报告的属性的配置信息，请参阅[Power View 报表属性](../../analysis-services/tabular-models/power-view-reporting-properties-ssas-tabular.md)。  
  
|属性|默认设置|Description|  
|--------------|---------------------|-----------------|  
|**默认字段集**|||  
|表行为|||  
  
##  <a name="bkmk_config_prop"></a> 配置表属性设置  
  
1.  在模型设计器中的数据视图中，单击某个表（选项卡）；或在关系图视图中，单击某个表头。  
  
2.  在 **“属性”** 窗口中，单击某个属性，然后键入值或单击其他配置选项的按钮。  
  
  
