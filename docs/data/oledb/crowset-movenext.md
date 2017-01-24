---
title: "CRowset::MoveNext | Microsoft Docs"
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
  - "ATL.CRowset<TAccessor>.MoveNext"
  - "ATL.CRowset.MoveNext"
  - "ATL::CRowset<TAccessor>::MoveNext"
  - "CRowset<TAccessor>.MoveNext"
  - "CRowset.MoveNext"
  - "CRowset<TAccessor>::MoveNext"
  - "CRowset::MoveNext"
  - "ATL::CRowset::MoveNext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveNext メソッド"
ms.assetid: 0df3288c-2bce-494f-99c0-6344b54a4adf
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::MoveNext
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

次のレコードにカーソルを移動します。  
  
## 構文  
  
```  
  
      HRESULT MoveNext( ) throw( );   
HRESULT MoveNext(   
   LONG lSkip,   
   bool bForward = true    
) throw( );  
```  
  
#### パラメーター  
 `lSkip`  
 \[\]フェッチする前にスキップ列番号。  
  
 `bForward`  
 \[\]次のレコード、後方に **false** に移動するに **true** を渡します。  
  
## 戻り値  
 標準の `HRESULT` を返します。  行セットの終わりに到達した場合、**DB\_S\_ENDOFROWSET**を返します。  
  
## 解説  
 前の位置を保持する `CRowset` オブジェクトから次の連続する行をフェッチします。  必要に応じて、行の先頭に `lSkip` をスキップしたり移動することもできます。  
  
 このメソッドは、行セットを含むテーブルまたはコマンドの **開く** を呼び出す前に次のプロパティを設定する必要があります:  
  
-   **DBPROP\_CANSCROLLBACKWARDS** は `lSkip` \< 場合は 0 `VARIANT_TRUE` である必要があります。  
  
-   **DBPROP\_CANFETCHBACKWARDS** は `bForward` \= false `VARIANT_TRUE` である必要があります。  
  
 それ以外 `lSkip` \> \(\= 0 と `bForward` \= true\)、追加のプロパティを設定する必要はありません。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CRowset クラス](../Topic/CRowset%20Class.md)   
 [CRowset::MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [CRowset::MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)