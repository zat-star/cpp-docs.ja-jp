---
title: "CBulkRowset::MoveToBookmark | Microsoft Docs"
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
  - "CBulkRowset<TAccessor>::MoveToBookmark"
  - "CBulkRowset.MoveToBookmark"
  - "MoveToBookmark"
  - "ATL.CBulkRowset.MoveToBookmark"
  - "CBulkRowset::MoveToBookmark"
  - "ATL::CBulkRowset<TAccessor>::MoveToBookmark"
  - "ATL::CBulkRowset::MoveToBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToBookmark メソッド"
ms.assetid: 76aab025-819e-4ecd-ae0a-d8d3fb2d2099
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBulkRowset::MoveToBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ブックマークに含めるか、ブックマークの指定されたオフセット \(`lSkip`\) で行を示す行フェッチします。  
  
## 構文  
  
```  
  
      HRESULT MoveToBookmark(  
   const CBookmarkBase& bookmark,  
   DBCOUNTITEM lSkip = 0   
) throw( );  
```  
  
#### パラメーター  
 `bookmark`  
 \[\]データをフェッチしたい位置を示す A のブックマークを設定します。  
  
 `lSkip`  
 \[\]ブックマークから対象の行への行数。  `lSkip` がゼロの場合、フェッチされる最初の行は、ブックマークの設定された行です。  `lSkip` が 1 の場合、フェッチされる最初の行は、行の後で設定された行です。  `lSkip` が–1 の場合、フェッチされる最初の行は、行にブックマーク行です。  
  
## 戻り値  
 *OLE DB Programmer's Reference*の [IRowset::GetData](https://msdn.microsoft.com/en-us/library/ms716988.aspx) を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CBulkRowset クラス](../Topic/CBulkRowset%20Class.md)