---
title: "コンパイラ エラー C2828 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2828"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2828"
ms.assetid: d8df6ed4-5954-46c2-b59b-52881d4e923d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C2828
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator operator' を、オブジェクトの外側で 2 項形式にすることはできません。  
  
 演算子をオブジェクトの外側で二項形式にすることはできません。  
  
### 次のような解決策を使用して問題を解決するには  
  
1.  オーバーロードされた演算子をオブジェクトに対してローカルにします。  
  
2.  オーバーロード対象として適切な単項演算子を選択します。