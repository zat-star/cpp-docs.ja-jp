---
title: "duration_values 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "chrono/std::chrono::duration_values"
dev_langs: 
  - "C++"
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# duration_values 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[duration](../standard-library/duration-class.md) テンプレート パラメーター `Rep` に特定の値を指定します。  
  
## 構文  
  
```  
template<class Rep>  
   struct duration_values;  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[duration\_values::max メソッド](../Topic/duration_values::max%20Method.md)|静的。  `Rep` 型の値の上限を指定します。|  
|[duration\_values::min メソッド](../Topic/duration_values::min%20Method.md)|静的。  `Rep` 型の値の下限を指定します。|  
|[duration\_values::zero メソッド](../Topic/duration_values::zero%20Method.md)|静的。  `Rep(0)` を返します。|  
  
## 必要条件  
 **ヘッダー:** chrono  
  
 **名前空間:** std::chrono  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)