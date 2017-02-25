---
title: "auto_rename | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "auto_rename"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_rename 属性"
ms.assetid: 1075f3ab-f6fc-4e04-8e22-ebe02695a567
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# auto_rename
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 固有の仕様**  
  
 潜在的な名前の競合を解決するため、変数名に 2 つのアンダースコア \(\_\_\) を追加して C\+\+ の予約語の名前を変更します。  
  
## 構文  
  
```  
auto_rename  
```  
  
## 解説  
 この属性は、変数名として C\+\+ の予約語 \(キーワードまたはマクロ\) を使用しているタイプ ライブラリをインポートするときに使用します。  
  
 **END C\+\+ 固有の仕様**  
  
## 参照  
 [\#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import ディレクティブ](../Topic/%23import%20Directive%20\(C++\).md)