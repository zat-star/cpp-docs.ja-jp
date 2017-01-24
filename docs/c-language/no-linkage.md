---
title: "リンケージなし | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "リンケージ [C++], なし"
  - "リンケージなし"
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# リンケージなし
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ブロック内の識別子の宣言に `extern` ストレージ クラス指定子が含まれていない場合、その識別子はリンケージを持たず、関数に対して一意になります。  
  
 次の識別子にはリンケージがありません。  
  
-   オブジェクトまたは関数以外として宣言された識別子  
  
-   関数パラメーターとして宣言された識別子  
  
-   `extern` ストレージ クラス指定子なしで宣言されたオブジェクトのブロック スコープ指定子  
  
 識別子にリンケージがない場合、同じスコープ レベルで同じ名前を再度 \(宣言子または型指定子で\) 宣言すると、シンボルの再定義エラーが発生します。  
  
## 参照  
 [extern を使用したリンケージの指定](../cpp/using-extern-to-specify-linkage.md)