---
title: "独自クラスのための &gt;&gt; 演算子のオーバーロード | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "演算子 >>, オーバーロード (独自のクラスの)"
  - "operator>>"
  - "operator>>, オーバーロード (独自のクラスの)"
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 独自クラスのための &gt;&gt; 演算子のオーバーロード
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

入力ストリームは、基本データ型で抽出 \(`>>`\) 演算子を使用します。  独自の型に抽出のような演算子を作成できます。; 成功は空白の正確な使用によって異なります。  
  
 既に説明したとおり `Date` クラスのストリーム演算子の例を次に示します。:  
  
```  
istream& operator>> ( istream& is, Date& dt )  
{  
   is >> dt.mo >> dt.da >> dt.yr;  
   return is;  
}  
```  
  
## 参照  
 [入力ストリーム](../standard-library/input-streams.md)