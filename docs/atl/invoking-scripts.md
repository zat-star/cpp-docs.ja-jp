---
title: "スクリプトの呼び出し | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "StringRegister"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "スクリプト, 起動 (ATL のレジストリを)"
  - "StringRegister メソッド"
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# スクリプトの呼び出し
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[を使用して置き換え可能パラメーター \(レジストラー プリプロセッサ\)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) は、置換のマップについて説明し、レジストラー メソッド **AddReplacement**を示します。  レジストラーは、スクリプトに特定の 8 つが他のメソッドがあり、すべてを次の表に示します。  
  
|メソッド|構文と説明|  
|----------|-----------|  
|**ResourceRegister**|**HRESULT ResourceRegister\( LPCOLESTR** の*resFileName***, UINT** `nID`**, LPCOLESTR** `szType`\) ;<br /><br /> モジュールのリソースに含まれているスクリプトを登録します。  *resFileName は*、モジュールの UNC パス自体を示します。  `nID` と `szType` は、リソースの ID と型を、それぞれ含まれています。|  
|**ResourceUnregister**|**HRESULT ResourceUnregister\( LPCOLESTR** の*resFileName***, UINT** `nID`**, LPCOLESTR** `szType`\) ;<br /><br /> を解除し、モジュールのリソースに含まれているスクリプト。  *resFileName は*、モジュールの UNC パス自体を示します。  `nID` と `szType` は、リソースの ID と型を、それぞれ含まれています。|  
|**ResourceRegisterSz**|**HRESULT ResourceRegisterSz\( LPCOLESTR** の*resFileName の***, LPCOLESTR** の*szID***, LPCOLESTR** `szType`\) ;<br /><br /> モジュールのリソースに含まれているスクリプトを登録します。  *resFileName は*、モジュールの UNC パス自体を示します。  *szID* と `szType` は、リソース文字列の識別子と型を、それぞれ含まれています。|  
|**ResourceUnregisterSz**|**HRESULT ResourceUnregisterSz\( LPCOLESTR** の*resFileName の***, LPCOLESTR** の*szID***, LPCOLESTR** `szType`\) ;<br /><br /> を解除し、モジュールのリソースに含まれているスクリプト。  *resFileName は*、モジュールの UNC パス自体を示します。  *szID* と `szType` は、リソース文字列の識別子と型を、それぞれ含まれています。|  
|**FileRegister**|**HRESULT FileRegister\( LPCOLESTR** の*ファイル名* \) ;<br /><br /> ファイルのスクリプトを登録します。  *ファイル名は* 、\(または\) リソース スクリプトを含むファイルへ UNC パスです。|  
|**FileUnregister**|**HRESULT FileUnregister\( LPCOLESTR** の*ファイル名* \) ;<br /><br /> ファイルのスクリプト登録解除します。  *ファイル名は* 、\(または\) リソース スクリプトを含むファイルへ UNC パスです。|  
|**StringRegister**|**HRESULT StringRegister\( LPCOLESTR** の*データ* \) ;<br /><br /> 文字列のスクリプトを登録します。  *データは* 、スクリプト自体が含まれます。|  
|**StringUnregister**|**HRESULT StringUnregister\( LPCOLESTR** の*データ* \) ;<br /><br /> 文字列のスクリプト登録解除します。  *データは* 、スクリプト自体が含まれます。|  
  
 **ResourceRegisterSz** と **ResourceUnregisterSz**は、**ResourceRegister** と **ResourceUnregister**に似ていますが、文字列の識別子を指定することができます。  
  
 リソース スクリプトが必要としない、または独自のファイルのスクリプトを作成する場合は、メソッド **FileRegister** と **FileUnregister** と便利です。  メソッド **StringRegister** と **StringUnregister** は .rgs ファイルが動的に割り当てられた文字列に格納されるようにします。  
  
## 参照  
 [レジストラー スクリプトの作成](../Topic/Creating%20Registrar%20Scripts.md)