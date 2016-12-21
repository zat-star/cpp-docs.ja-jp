---
title: "CString の評価 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "代入ステートメント, 割り当て (CString オブジェクトの)"
  - "CString オブジェクト, 代入の意味"
  - "意味 (Cstring での)"
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CString の評価
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CString](../atl-mfc-shared/reference/cstringt-class.md) のオブジェクトが拡大できる動的オブジェクトである場合も、これらは組み込みのプリミティブ型、および単純なクラスと同様に動作します。  `CString` の各オブジェクトは、一意の値を表します。  文字列への`CString` のオブジェクトは、に関するように、実際の文字列ポインターではなくしてください。  
  
 別の **CString** の 1 種類のオブジェクトを代入できます。  ただし、`CString` の 2 種類のオブジェクトの 1 つを変更すると、`CString` の他のオブジェクトには、次の例に示すように、変更できません:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/CPP/cstring-semantics_1.cpp)]  
  
 同じ文字列を表すため `CString` の 2 種類のオブジェクトが等しい「例」見なされることに注意してください。  `CString` のクラスは、ID \(アドレスではなく\) 値 \(内容\) に基づいて `CString` の 2 種類のオブジェクトを比較するには、等値演算子 \(`==`\) をオーバーロードします。  
  
## 参照  
 [文字列](../atl-mfc-shared/strings-atl-mfc.md)