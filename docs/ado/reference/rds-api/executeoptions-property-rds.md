---
title: "ExecuteOptions 属性 (RDS) |Microsoft 文档"
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
helpviewer_keywords:
- ExecuteOptions property [ADO], VBScript example
ms.assetid: 62a4fd88-afc3-4f1f-b978-40710a30c4e9
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 7cc52b6deb9915abd9f90b8596edee5ded07f816
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="executeoptions-property-rds"></a>ExecuteOptions 属性 (RDS)
指示是否启用异步执行。  
  
> [!IMPORTANT]
>  从 Windows 8 和 Windows Server 2012 开始，不再在 Windows 操作系统中包含 RDS 服务器组件 (请参阅 Windows 8 和[Windows Server 2012 兼容性手册](https://www.microsoft.com/en-us/download/details.aspx?id=27416)有关详细信息)。 将 Windows 的未来版本中删除 RDS 客户端组件。 请避免在新的开发工作中使用该功能，并着手修改当前还在使用该功能的应用程序。 使用 RDS 的应用程序应迁移到[WCF 数据服务](http://go.microsoft.com/fwlink/?LinkId=199565)。  
  
## <a name="settings-and-return-values"></a>设置和返回值  
 设置或返回下列值之一。  
  
|常量|Description|  
|--------------|-----------------|  
|**adcExecSync**|执行的下一步刷新[记录集](../../../ado/reference/ado-api/recordset-object-ado.md)同步。|  
|**adcExecAsync**|默认值。 执行的下一步刷新**记录集**以异步方式。|  
  
> [!NOTE]
>  使用这些常量的每个可执行文件必须提供其声明。 你可剪切并粘贴文件 Adcvbs.inc，位于 RDS 库的默认安装文件夹中的所需的常量声明。  
  
## <a name="remarks"></a>注释  
 如果**ExecuteOptions**设置为**adcExecAsync**，则这以异步方式执行下一步，则**刷新**上调用[rds.DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md)对象的**记录集**。  
  
 如果你尝试调用[重置](../../../ado/reference/rds-api/reset-method-rds.md)，[刷新](../../../ado/reference/rds-api/refresh-method-rds.md)， [SubmitChanges](../../../ado/reference/rds-api/submitchanges-method-rds.md)，[正在执行](../../../ado/reference/ado-api/cancelupdate-method-ado.md)，或[记录集](../../../ado/reference/rds-api/recordset-sourcerecordset-properties-rds.md)尽管可能会更改的另一个异步操作[rds.DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md)对象的**记录集**正在执行，则会出错。  
  
 如果一个异步操作过程中发生错误**rds.DataControl**对象的[ReadyState](../../../ado/reference/rds-api/readystate-property-rds.md)值发生更改时从**adcReadyStateLoaded**到**adcReadyStateComplete**，和**记录集**属性的值保持*执行任何操作*。  
  
## <a name="applies-to"></a>适用范围  
 [DataControl 对象 (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)  
  
## <a name="see-also"></a>另请参阅  
 [ExecuteOptions 和 FetchOptions 属性示例 (VBScript)](../../../ado/reference/rds-api/executeoptions-and-fetchoptions-properties-example-vbscript.md)   
 [Cancel 方法 (RDS)](../../../ado/reference/rds-api/cancel-method-rds.md)


