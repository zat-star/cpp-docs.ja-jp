---
title: "treat_as_floating_point 構造体 | Microsoft Docs"
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
  - "chrono/std::chrono::treat_as_floating_point"
dev_langs: 
  - "C++"
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
caps.latest.revision: 13
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# treat_as_floating_point 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`Rep` を浮動小数点型として扱うことができるかどうかを指定します。  
  
## 構文  
  
```  
template<class Rep>  
struct treat_as_floating_point : is_floating_point<Rep>;  
```  
  
## 解説  
 `Rep` は、特殊化 `treat_as_floating_point<Rep>` が [true\_type](../Topic/true_type%20Typedef.md) から派生したときにのみ浮動小数点型として処理できます。  このテンプレート クラスは、ユーザー定義型に特殊化することができます。  
  
## 必要条件  
 **ヘッダー:** chrono  
  
 **名前空間:** std::chrono  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)