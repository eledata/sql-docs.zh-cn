---
title: "RestoreEncryptionKey 方法 (WMI MSReportServer_ConfigurationSetting) |Microsoft 文档"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- RestoreEncryptionKey (WMI MSReportServer_ConfigurationSetting Class)
apilocation:
- reportingservices.mof
apitype: MOFDef
helpviewer_keywords:
- RestoreEncryptionKey method
ms.assetid: 37e949f5-15af-4858-848a-f482ee94fcd9
caps.latest.revision: 18
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: 38352086b908fe064ce3e16d7502094ba0c13d50
ms.contentlocale: zh-cn
ms.lasthandoff: 08/09/2017

---
# <a name="configurationsetting-method---restoreencryptionkey"></a>ConfigurationSetting 方法-RestoreEncryptionKey
  将指定的加密密钥重新应用于报表服务器数据库。  
  
## <a name="syntax"></a>语法  
  
```vb  
Public Sub RestoreEncryptionKey(ByRef KeyFile() As Integer, _  
    ByRef Length As Int32, ByVal Password As String, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void RestoreEncryptionKey(out Byte[] KeyFile, out Int32 Length,   
            string Password, out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a>Parameters  
 *KeyFile[]*  
 [out] 包含已加密的加密密钥的数组。  
  
 *长度*  
 [out] 该方法返回的数组长度。  
  
 *密码*  
 用于对加密密钥进行加密的字符串。  
  
 *HRESULT*  
 [out] 指示调用是成功还是失败的值。  
  
 *ExtendedErrors[]*  
 [out] 一个字符串数组，包含此调用返回的其他错误。  
  
## <a name="return-value"></a>返回值  
 返回 *HRESULT* ，指示方法调用是成功还是失败。 值 0 指示方法调用已成功。 非零值指示已发生错误。  
  
## <a name="remarks"></a>注释  
 如果报表服务器数据库中已经存在报表服务器的条目，则删除它。 然后，使用指定的加密密钥和报表服务器的公钥创建新条目。  
  
 在调用清除加密密钥列表的 [DeleteEncryptionKey](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-deleteencryptionkey.md) 方法之后调用该方法最有效。  
  
## <a name="requirements"></a>要求  
 **Namespace:**[!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [MSReportServer_ConfigurationSetting 成员](../../reporting-services/wmi-provider-library-reference/msreportserver-configurationsetting-members.md)  
  
  