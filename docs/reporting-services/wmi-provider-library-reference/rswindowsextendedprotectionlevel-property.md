---
title: "RSWindowsExtendedProtectionLevel 属性 | Microsoft Docs"
ms.custom: 
ms.date: 03/20/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.service: 
ms.component: wmi-provider-library-reference
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 162ffe86-69c3-49d2-b9ed-49d097c05551
caps.latest.revision: "6"
author: markingmyname
ms.author: maghan
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 2df0986f8bdf40a87a53d23ea97532142486f1e0
ms.sourcegitcommit: 7e117bca721d008ab106bbfede72f649d3634993
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2018
---
# <a name="rswindowsextendedprotectionlevel-property"></a>RSWindowsExtendedProtectionLevel 属性
  返回一个字符串值，该值指示配置报表服务器所支持的保护级别。 该属性为只读。  
  
## <a name="syntax"></a>语法  
  
```vb  
Public Dim RSWindowsExtendedProtectionLevel As String  
```  
  
```csharp  
public string RSWindowsExtendedProtectionLevel;  
```  
  
## <a name="remarks"></a>Remarks  
 返回一个字符串值，该值指示配置报表服务器所支持的保护级别。 如果 WMI 提供程序连接到的报表服务器不支持扩展保护，则返回“”（空字符串）。 下表显示有效值：  
  
 `“Off” | “Allow” | “Require”`  
  
## <a name="example-code"></a>示例代码  
 [MSReportServer_ConfigurationSetting 类](../../reporting-services/wmi-provider-library-reference/msreportserver-configurationsetting-class.md)  
  
## <a name="see-also"></a>另请参阅  
 [RSWindowsExtendedProtectionScenario 属性 (WMI MSReportServer_ConfigurationSetting)](../../reporting-services/wmi-provider-library-reference/rswindowsextendedprotectionscenario-property.md)   
 [SetExtendedProtectionSettings 方法 (WMI MSReportServer_ConfigurationSetting)](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-setextendedprotectionsettings.md)   
 [Reporting Services 针对验证的扩展保护](../../reporting-services/security/extended-protection-for-authentication-with-reporting-services.md)   
 [RsReportServer.config 配置文件](../../reporting-services/report-server/rsreportserver-config-configuration-file.md)  
  
  
