---
title: 数据源数据类型 (ASSL) |Microsoft 文档
ms.custom: ''
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- DataSource Data Type
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- DataSource data type
ms.assetid: 05e8de8d-452d-4128-98a6-4437df227fec
caps.latest.revision: 13
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 68997a04b74297bdd56991110d5a1fe2d77dd33c
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="datasource-data-type-assl"></a>DataSource 数据类型 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]定义表示中的数据源的抽象基元数据类型[数据库](../../../analysis-services/scripting/objects/database-element-assl.md)元素。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<DataSource>  
   <Name>...</Name>  
   <ID>...</ID>  
   <CreatedTimestamp>...</CreateTimestamp>  
   <LastSchemaUpdate>...</LastSchemaUpdate>  
   <ManagedProvider>...</ManagedProvider>  
   <ConnectionString>...</ConnectionString>  
   <ConnectionStringSecurity>...</ConnectionStringSecurity>  
   <ImpersonationInfo>...</ImpersonationInfo>  
   <Isolation>...</Isolation>  
   <MaxActiveConnections>...</MaxActiveConnections>  
   <Description>...</Description>  
   <Timeout>...</Timeout>  
   <Annotations>...</Annotations>  
   <DataSourcePermission>...</DataSourcePermission>  
</DataSource>  
```  
  
## <a name="data-type-characteristics"></a>数据类型特征  
  
|特征|Description|  
|--------------------|-----------------|  
|基本数据类型|InclusionThresholdSetting|  
|派生数据类型|[RelationalDataSource](../../../analysis-services/scripting/data-type/relationaldatasource-data-type-assl.md)， [OlapDataSource](../../../analysis-services/scripting/data-type/olapdatasource-data-type-assl.md)， [PushedDataSource](../../../analysis-services/scripting/data-type/pusheddatasource-data-type-assl.md)|  
  
## <a name="data-type-relationships"></a>数据类型关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|InclusionThresholdSetting|  
|子元素|[批注](../../../analysis-services/scripting/collections/annotations-element-assl.md)， [ConnectionString](../../../analysis-services/scripting/properties/connectionstring-element-assl.md)， [ConnectionStringSecurity](../../../analysis-services/scripting/properties/connectionstringsecurity-element-assl.md)， [CreatedTimestamp](../../../analysis-services/scripting/properties/createdtimestamp-element-assl.md)， [DataSourcePermission](../../../analysis-services/scripting/collections/datasourcepermissions-element-assl.md)，[说明](../../../analysis-services/scripting/properties/description-element-assl.md)， [ID](../../../analysis-services/scripting/properties/id-element-assl.md)， [ImpersonationInfo](../../../analysis-services/scripting/properties/impersonationinfo-element-assl.md)，[隔离](../../../analysis-services/scripting/properties/isolation-element-assl.md)， [LastSchemaUpdate](../../../analysis-services/scripting/properties/lastschemaupdate-element-assl.md)， [ManagedProvider](../../../analysis-services/scripting/properties/managedprovider-element-assl.md)， [MaxActiveConnections](../../../analysis-services/scripting/properties/maxactiveconnections-element-assl.md)，[名称](../../../analysis-services/scripting/properties/name-element-assl.md)，[超时](../../../analysis-services/scripting/properties/timeout-element-assl.md)|  
|派生元素|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Remarks  
 定义的外部绑定时**名称**元素是可选的。 无需指定**名称**元素允许要在多维数据集、 分区和等等的绑定中定义的数据源。 有关包含的数据源**数据库**元素，**名称**是必需的元素。  
  
 有关数据源的详细信息，请参阅 [Data Sources in Multidimensional Models](../../../analysis-services/multidimensional-models/data-sources-in-multidimensional-models.md)。  
  
 分析管理对象 (AMO) 对象模型中的相应元素是<xref:Microsoft.AnalysisServices.DataSource>。  
  
## <a name="see-also"></a>另请参阅  
 [Analysis Services 脚本语言 XML 数据类型 &#40;ASSL &#41;](../../../analysis-services/scripting/data-type/analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
