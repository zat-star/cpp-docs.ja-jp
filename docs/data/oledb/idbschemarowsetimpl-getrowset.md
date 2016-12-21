---
title: "IDBSchemaRowsetImpl::GetRowset | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IDBSchemaRowsetImpl::GetRowset"
  - "ATL.IDBSchemaRowsetImpl.GetRowset"
  - "IDBSchemaRowsetImpl<SessionClass>::GetRowset"
  - "IDBSchemaRowsetImpl.GetRowset"
  - "IDBSchemaRowsetImpl::GetRowset"
  - "ATL::IDBSchemaRowsetImpl<SessionClass>::GetRowset"
  - "GetRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRowset メソッド"
ms.assetid: 3ae28c22-e186-4a15-8591-b0192e784a6f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBSchemaRowsetImpl::GetRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スキーマ行セットを返します。  
  
## 構文  
  
```  
  
STDMETHOD (GetRowset)(  
   IUnknown *  
pUnkOuter  
,  
   REFGUID   
rguidSchema  
,  
   ULONG   
cRestrictions  
,  
   const VARIANT   
rgRestrictions  
[],  
   REFIID   
riid  
,  
   ULONG   
cPropertySets  
,  
   DBPROPSET   
rgPropertySets  
[],  
   IUnknown **  
ppRowset  
);  
  
```  
  
#### パラメーター  
 `pUnkOuter`  
 \[入力\] 集約時は外部 **IUnknown**。それ以外の場合は **NULL**。  
  
 `rguidSchema`  
 \[入力\] 要求するスキーマ行セット GUID \(`DBSCHEMA_TABLES` など\) への参照。  
  
 `cRestrictions`  
 \[入力\] 行セットに適用する制限の数。  
  
 `rgRestrictions`  
 \[入力\] 制限を表す `cRestrictions` 個の **VARIANT** の配列。  
  
 `riid`  
 \[入力\] 新しく作成されたスキーマ行セットに対して要求する IID。  
  
 `cPropertySets`  
 \[入力\] 設定するプロパティ セットの数。  
  
 `rgPropertySets`  
 \[入力\/出力\] 新しく作成されたスキーマ行セットに対して設定する [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 構造体の配列。  
  
 `ppRowset`  
 \[出力\] 新しく作成されたスキーマ行セットに対して要求するインターフェイスへのポインター。  
  
## 解説  
 このメソッドを使用するには、ユーザーはセッション クラスにスキーマ マップを持っている必要があります。`GetRowset` は、`rguidSchema` パラメーターがいずれかのマップ エントリの GUID と一致する場合、スキーマ マップ情報に基づき、指定された行セット オブジェクトを作成します。 マップ エントリについては、「[SCHEMA\_ENTRY](../../data/oledb/schema-entry.md)」を参照してください。  
  
 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] の「[IDBSchemaRowset::GetRowset](https://msdn.microsoft.com/en-us/library/ms722634.aspx)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IDBSchemaRowsetImpl クラス](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](http://msdn.microsoft.com/ja-jp/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [IDBSchemaRowsetImpl::GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)   
 [スキーマ行セット クラスと Typedef クラス](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md)