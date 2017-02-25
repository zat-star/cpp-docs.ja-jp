---
title: "CDBErrorInfo クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBErrorInfo"
  - "ATL::CDBErrorInfo"
  - "ATL.CDBErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBErrorInfo クラス"
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# CDBErrorInfo クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB の [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) インターフェイスを使用して処理する OLE DB のエラーをサポートします。  
  
## 構文  
  
```  
class CDBErrorInfo  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md)|エラー レコードに含まれるすべてのエラー情報を返します。|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|[IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx) を指定されたエラーについての基本情報を取得します。|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|[IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) をカスタム エラー オブジェクトのインターフェイスへのポインターを取得します。|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|[IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) を指定されたレコードに **IErrorInfo** インターフェイス ポインターを取得します。|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|[IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/en-us/library/ms715793.aspx) をエラー パラメーターを取得します。|  
|[GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md)|指定されたオブジェクトのエラー レコードを取得します。|  
  
## 解説  
 このインターフェイスは、ユーザー レコードに一つ以上のエラーを返します。  エラー レコードの値を取得するに [CDBErrorInfo::GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md) は、最初に呼び出されます。  その後、各レコードのエラー情報を取得するためにアクセス関数の 1 を、[CDBErrorInfo::GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md)など\) を呼び出します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [DBViewer](../../top/visual-cpp-samples.md)   
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)