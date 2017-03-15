---
title: "CRowset::MoveToRatio | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MoveToRatio"
  - "CRowset<TAccessor>::MoveToRatio"
  - "CRowset::MoveToRatio"
  - "CRowset<TAccessor>.MoveToRatio"
  - "ATL.CRowset.MoveToRatio"
  - "ATL::CRowset::MoveToRatio"
  - "CRowset.MoveToRatio"
  - "ATL.CRowset<TAccessor>.MoveToRatio"
  - "ATL::CRowset<TAccessor>::MoveToRatio"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToRatio メソッド"
ms.assetid: 1fa313bd-8fd1-4608-8e85-44993b97dd88
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CRowset::MoveToRatio
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

フェッチは行セットの分数で表現した位置から開始します。  
  
## 構文  
  
```  
  
      HRESULT MoveToRatio(   
   DBCOUNTITEM nNumerator,   
   DBCOUNTITEM nDenominator,   
   bool bForward = true    
) throw( );  
```  
  
#### パラメーター  
 `nNumerator`  
 \[\]がの小数部の位置がデータをフェッチする型を決定するために使用される分子\)。  
  
 `nDenominator`  
 \[\]がの小数部の位置がデータをフェッチする型を決定するために使用される分母\)。  
  
 `bForward`  
 \[\]前方または後方に移動するかどうかを示します。  既定は前方です。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 `MoveToRatio` は 次の数式にほぼ一致する行をフェッチします:  
  
 `( nNumerator *  RowsetSize ) / nDenominator`  
  
 `RowsetSize` が行セット単位であるため、行が使用されます。  この数式の精度は特定のプロバイダーによって異なります。  詳細については、「[IRowsetScroll::GetRowsAtRatio](https://msdn.microsoft.com/en-us/library/ms709602.aspx)」を参照してください。  
  
 このメソッドは、すべてのプロバイダーでサポートされない省略可能なインターフェイス `IRowsetScroll`が必要ですが、; この場合、メソッドの戻り **E\_NOINTERFACE**。  また `VARIANT_TRUE` にテーブルの **開く** を呼び出す前に **DBPROP\_IRowsetScroll** を設定または命じなければ、行セットが含まれます。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CRowset クラス](../Topic/CRowset%20Class.md)