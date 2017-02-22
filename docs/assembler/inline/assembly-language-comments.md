---
title: "アセンブリ言語のコメント | Microsoft Docs"
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
  - "__asm キーワード [C++], 命令"
  - "アセンブリ言語 [C++], コメント"
  - "コメント [C++], アセンブリ言語"
  - "マクロ [C++], アセンブリ言語"
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# アセンブリ言語のコメント
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 `__asm` ブロックはアセンブリ言語命令コメントを使用する :  
  
```  
__asm mov ax, offset buff ; Load address of buff  
```  
  
 C のマクロが一つの論理行に配置するためマクロでアセンブリ言語のコメントを使用しないでください。  \([C マクロと \_\_asm ブロックを定義できます。](../../assembler/inline/defining-asm-blocks-as-c-macros.md) を参照してください\)。`__asm` ブロックはC スタイルのコメントを含めることができます。; 詳細については[\_\_asm ブロックの C または C\+\+ を使用する](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) を参照してください。  
  
 **終了 Microsoft 固有の仕様→**  
  
## 参照  
 [\_\_asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)