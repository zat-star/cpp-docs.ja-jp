---
title: "no_auto_exclude | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "no_auto_exclude"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "no_auto_exclude 属性"
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# no_auto_exclude
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 固有の仕様**  
  
 自動除外を無効にします。  
  
## 構文  
  
```  
no_auto_exclude  
```  
  
## 解説  
 タイプ ライブラリは、システム ヘッダーまたはその他のタイプ ライブラリで定義された項目の定義を含むことがあります。  `#import` は、そのような項目を自動的に除外して多重定義エラーを回避します。  これが実行されると、除外する各項目に対して [コンパイラの警告 \(レベル 3\) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) が発行されます。  この自動除外を、この属性を使用して無効にすることができます。  
  
 **END C\+\+ 固有の仕様**  
  
## 参照  
 [\#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import ディレクティブ](../Topic/%23import%20Directive%20\(C++\).md)