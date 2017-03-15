---
title: "raw_method_prefix | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "raw_method_prefix"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "raw_method_prefix 属性"
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# raw_method_prefix
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 固有の仕様**  
  
 名前の衝突を避けるために異なるプレフィックスを指定します。  
  
## 構文  
  
```  
raw_method_prefix("Prefix")  
```  
  
#### パラメーター  
 `Prefix`  
 使用されるプレフィックス。  
  
## 解説  
 低水準のプロパティとメソッドは、高水準のエラー処理メンバー関数との名前の衝突を回避するために、名前に既定で **raw\_** というプレフィックスが付いたメンバー関数によって公開されます。  
  
> [!NOTE]
>  [raw\_interfaces\_only](#_predir_raw_interfaces_only) 属性を使用しても、`raw_method_prefix` 属性の効果は変わりません。  `raw_method_prefix` は、プレフィックスの指定において、常に `raw_interfaces_only` に優先します。  両方の属性を同じ `#import` ステートメントで使用した場合、`raw_method_prefix` 属性で指定されているプレフィックスが使用されます。  
  
 **END C\+\+ 固有の仕様**  
  
## 参照  
 [\#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import ディレクティブ](../Topic/%23import%20Directive%20\(C++\).md)