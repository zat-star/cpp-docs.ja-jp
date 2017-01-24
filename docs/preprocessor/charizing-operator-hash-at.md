---
title: "文字定数化演算子 (#@) | Microsoft Docs"
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
  - "#@"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#@ プリプロセッサ演算子"
  - "文字定数化演算子"
  - "プリプロセッサ, 演算子"
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 文字定数化演算子 (#@)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 文字定数化演算子は、マクロの引数でのみ使用できます。  マクロ定義の仮パラメーターの前に **\#@** を指定すると、実際の引数は一重引用符で囲まれ、マクロを展開するときに文字として扱われます。  次に例を示します。  
  
```  
#define makechar(x)  #@x  
```  
  
 は、次のステートメント  
  
```  
a = makechar(b);  
```  
  
 を次のように展開します  
  
```  
a = 'b';  
```  
  
 単一引用符文字は charizing 演算子では使用できません。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)