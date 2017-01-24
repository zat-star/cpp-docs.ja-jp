---
title: "high_method_prefix | Microsoft Docs"
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
  - "high_method_prefix"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "high_method_prefix 属性"
ms.assetid: cacebf09-12f5-4919-ad40-939e206e340c
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# high_method_prefix
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 固有の仕様**  
  
 高レベルのプロパティおよびメソッドの名前付けで使用されるプレフィックスを指定します。  
  
## 構文  
  
```  
high_method_prefix("Prefix")  
```  
  
#### パラメーター  
 `Prefix`  
 使用されるプレフィックス。  
  
## 解説  
 既定では、高度なエラー処理のプロパティとメソッドは、プレフィックスなしの名前のメンバー関数によって公開されます。  名前はタイプ ライブラリから取り込まれます。  
  
 **END C\+\+ 固有の仕様**  
  
## 参照  
 [\#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import ディレクティブ](../Topic/%23import%20Directive%20\(C++\).md)