---
title: "IDBSchemaRowsetImpl::CheckRestrictions | Microsoft Docs"
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
  - "CheckRestrictions"
  - "IDBSchemaRowsetImpl::CheckRestrictions"
  - "IDBSchemaRowsetImpl.CheckRestrictions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CheckRestrictions メソッド"
ms.assetid: 3c9d77d2-0e4b-48fa-80db-d735da19f1cf
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBSchemaRowsetImpl::CheckRestrictions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スキーマ行セットに対して制限の妥当性をチェックします。  
  
## 構文  
  
```  
  
HRESULT CheckRestrictions(  
   REFGUID   
rguidSchema  
,  
   ULONG   
cRestrictions  
,  
   const VARIANT   
rgRestrictions  
[]  
);  
  
```  
  
#### パラメーター  
 `rguidSchema`  
 \[入力\] 要求するスキーマ行セット GUID \(`DBSCHEMA_TABLES` など\) への参照。  
  
 `cRestrictions`  
 \[入力\] コンシューマーがスキーマ行セットに渡した制限の数。  
  
 `rgRestrictions`  
 \[入力\] 設定する制限値の長さ *cRestrictions* の配列。 詳細については、[SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) の `rgRestrictions` パラメーターの説明を参照してください。  
  
## 解説  
 `CheckRestrictions` を使用して、スキーマ行セットに対して制限の妥当性をチェックします。 CheckRestrictions は、`DBSCHEMA_TABLES`、**DBSCHEMA\_COLUMNS**、および **DBSCHEMA\_PROVIDER\_TYPES** の各スキーマ行セットの制限をチェックします。 これを呼び出して、コンシューマーの **IDBSchemaRowset::GetRowset** 呼び出しが正しいかどうかを判断してください。 上記以外のスキーマ行セットをサポートする場合は、このタスクを実行する独自の関数を作成する必要があります。  
  
 `CheckRestrictions` は、コンシューマーが、プロバイダーによってサポートされている正しい制限および制限の種類 \(文字列の場合は `VT_BSTR` など\) を持つ [GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) を呼び出しているかどうかを判断します。 また、正しい制限数がサポートされているかどうかも判断します。`CheckRestrictions` は、既定で [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) 呼び出しを通じて、任意の行セットについてプロバイダーがサポートしている制限の種類を確認します。 次に、コンシューマーが呼び出した制限とプロバイダーがサポートしている制限を比較することで、処理は成功または失敗します。  
  
 スキーマ行セットの詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] の *OLE DB プログラマーズ リファレンス*の「[IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IDBSchemaRowsetImpl クラス](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](http://msdn.microsoft.com/ja-jp/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [スキーマ行セット クラスと Typedef クラス](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md)