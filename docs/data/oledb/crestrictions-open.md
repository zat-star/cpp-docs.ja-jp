---
title: "CRestrictions::Open | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRestrictions.Open"
  - "ATL::CRestrictions::Open"
  - "ATL.CRestrictions.Open"
  - "CRestrictions::Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open メソッド"
ms.assetid: 0aff0cc3-543a-47d2-8d6b-ebb36926b6db
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRestrictions::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ユーザーが指定された制約に従って結果セットを返します。  
  
## 構文  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCTSTR lpszParam 1 = NULL,  
   LPCTSTR lpszParam 2 = NULL,  
   LPCTSTR lpszParam 3 = NULL,  
   LPCTSTR lpszParam 4 = NULL,  
   LPCTSTR lpszParam 5 = NULL,  
   LPCTSTR lpszParam 6 = NULL,  
   LPCTSTR lpszParam 7 = NULL,  
   bool bBind = true  
);  
```  
  
#### パラメーター  
 `session`  
 \[\]データ ソースへの接続に使用される既存のセッション オブジェクトを指定します。  
  
 *lpszParam*  
 \[\]スキーマ行セットに制限を指定します。  
  
 `bBind`  
 \[\]列マップを自動的にバインドするかどうかを指定します。  列マップを自動的にバインドします **true**は既定です。  手動でバインドできるように **false** に設定 `bBind` は、列マップの自動バインディングを防ぎます。\(手動バインドは、OLAP のユーザーに注目です\)。  
  
## 戻り値  
 `HRESULT` 標準値のいずれか 1 つが。  
  
## 解説  
 スキーマ行セットの最大 7 個の制限を指定できます。  
  
 各スキーマ行セットで定義されている制約については、" [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldbsch.h  
  
## 参照  
 [CRestrictions クラス](../Topic/CRestrictions%20Class.md)   
 [スキーマ行セット クラスと Typedef クラス](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md)