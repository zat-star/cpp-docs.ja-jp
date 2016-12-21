---
title: "コンパイラ エラー C2834 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2834"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2834"
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2834
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator operator' をクラスに対して局所的にすることはできません。  
  
 `new` 演算子と `delete` 演算子は、それぞれが置かれているクラスに結び付けられています。  スコープ解決演算子を使用して、他のクラスにある `new` または `delete` を選択することはできません。  複数の形式の `new` 演算子と `delete` 演算子を実装するには、余分の仮パラメーターを指定できる形式の演算子を作成します。