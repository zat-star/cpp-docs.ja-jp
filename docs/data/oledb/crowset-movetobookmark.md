---
title: "CRowset::MoveToBookmark | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CRowset::MoveToBookmark"
  - "ATL::CRowset<TAccessor>::MoveToBookmark"
  - "ATL.CRowset.MoveToBookmark"
  - "ATL.CRowset<TAccessor>.MoveToBookmark"
  - "MoveToBookmark"
  - "CRowset::MoveToBookmark"
  - "CRowset.MoveToBookmark"
  - "CRowset<TAccessor>::MoveToBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToBookmark メソッド"
ms.assetid: 90124723-8daf-4692-ae2f-0db26b5db920
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::MoveToBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ブックマークに含めるか、ブックマークの指定されたオフセット \(`lSkip`\) で行を示す行フェッチします。  
  
## 構文  
  
```  
  
      HRESULT MoveToBookmark(   
   const CBookmarkBase& bookmark,   
   LONG lSkip = 0    
) throw( );  
```  
  
#### パラメーター  
 `bookmark`  
 \[\]データをフェッチしたい位置を示す A のブックマークを設定します。  
  
 `lSkip`  
 \[\]ブックマークから対象の行への行数。  `lSkip` がゼロの場合、フェッチされる最初の行は、ブックマークの設定された行です。  `lSkip` が 1 の場合、フェッチされる最初の行は、行の後で設定された行です。  `lSkip` が–1 の場合、フェッチされる最初の行は、行にブックマーク行です。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 このメソッドは、すべてのプロバイダーでサポートされない省略可能なインターフェイス `IRowsetLocate`が必要ですが、; この場合、メソッドの戻り **E\_NOINTERFACE**。  また `VARIANT_TRUE` に **DBPROP\_IRowsetLocate** と `VARIANT_TRUE` にテーブルの **開く** を呼び出す前に設定 **DBPROP\_CANFETCHBACKWARDS** を設定または命じなければ、行セットが含まれます。  
  
 使用方法の詳細については、コンシューマーで、[ブックマークを使用する](../../data/oledb/using-bookmarks.md)ブックマークを参照します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CRowset クラス](../Topic/CRowset%20Class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [CRowset::MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [IRowsetLocate::GetRowsAt](https://msdn.microsoft.com/en-us/library/ms723031.aspx)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)