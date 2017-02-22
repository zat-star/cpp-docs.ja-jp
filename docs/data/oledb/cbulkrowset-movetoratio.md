---
title: "CBulkRowset::MoveToRatio | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CBulkRowset.MoveToRatio"
  - "ATL::CBulkRowset::MoveToRatio"
  - "MoveToRatio"
  - "CBulkRowset::MoveToRatio"
  - "ATL.CBulkRowset<TAccessor>.MoveToRatio"
  - "ATL::CBulkRowset<TAccessor>::MoveToRatio"
  - "ATL.CBulkRowset.MoveToRatio"
  - "CBulkRowset<TAccessor>::MoveToRatio"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToRatio メソッド"
ms.assetid: 86be60f5-9341-44c1-8e1e-9174c082d0d5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CBulkRowset::MoveToRatio
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

フェッチは行セットの分数で表現した位置から開始します。  
  
## 構文  
  
```  
  
      HRESULT MoveToRatio(  
   DBCOUNTITEM nNumerator,  
   DBCOUNTITEM nDenominator   
) throw( );  
```  
  
#### パラメーター  
 `nNumerator`  
 \[\]データをフェッチする分数で表現した位置を決定するために使用される分子\)。  
  
 `nDenominator`  
 \[\]データをフェッチする分数で表現した位置を決定するために使用される分母\)。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 `MoveToRatio` は 次の数式に基づいて、行を大きくフェッチします:  
  
 `( nNumerator *  RowsetSize ) / nDenominator`  
  
 `RowsetSize` が行セット単位であるため、行が使用されます。  この数式の精度は特定のプロバイダーによって異なります。  詳細については、*OLE DB Programmer's Reference*の [IRowsetScroll::GetRowsAtRatio](https://msdn.microsoft.com/en-us/library/ms709602.aspx) を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CBulkRowset クラス](../Topic/CBulkRowset%20Class.md)