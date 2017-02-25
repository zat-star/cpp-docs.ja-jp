---
title: "auto_inline | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "auto_inline_CPP"
  - "vc-pragma.auto_inline"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_inline プラグマ"
  - "プラグマ, auto_inline"
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# auto_inline
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**off** が指定された範囲内で定義されている関数を、自動インライン展開の候補と見なされないように除外します。  
  
## 構文  
  
```  
  
#pragma auto_inline( [{on | off}] )  
```  
  
## 解説  
 **auto\_inline** プラグマを使用するには、関数定義の前と直後に配置します \(関数定義の中には配置しません\)。  プラグマは、このプラグマが発生した後の最初の関数呼び出し時に有効になります。  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)