---
title: "NMAKE マクロの定義 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "定義 (NMAKE マクロを)"
  - "マクロ, NMAKE"
  - "NMAKE マクロ, 定義"
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# NMAKE マクロの定義
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
macroname=string  
```  
  
## 解説  
 *macroname* は、文字、数字、およびアンダースコア \(\_\) の 1,024 文字までの組み合わせで構成され、大文字と小文字が区別されます。  *macroname* には、呼び出しマクロを指定できます。  *macroname* が呼び出しマクロだけで構成される場合、呼び出されるマクロを null または未定義にすることはできません。  
  
 `string` には、0 個以上の文字のシーケンスを指定できます。  null 文字列は、文字がないか、または空白やタブだけで構成されます。  `string` には、マクロの呼び出しを指定できます。  
  
## さらに詳しくは次のトピックをクリックしてください  
 [マクロの特殊文字](../build/special-characters-in-macros.md)  
  
 [Null マクロと未定義マクロ](../build/null-and-undefined-macros.md)  
  
 [マクロを定義する場所](../Topic/Where%20to%20Define%20Macros.md)  
  
 [マクロ定義の優先順位](../build/precedence-in-macro-definitions.md)  
  
## 参照  
 [マクロと NMAKE](../Topic/Macros%20and%20NMAKE.md)