---
title: "noinline | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "noinline"
  - "noinline_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec キーワード [C++], noinline"
  - "noinline __declspec キーワード"
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# noinline
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 **\_\_declspec\(noinline\)** は、特定のメンバー関数 \(クラス内の関数\) をインラインにしないことをコンパイラに伝えます。  
  
 コードのパフォーマンスにとって大きな意味がなく、重要でなければ、関数をインラインにしない方がよい場合があります。  つまり、関数が小さく、頻繁に呼び出されないと考えられる場合 \(エラー条件を処理する関数など\)。  
  
 関数が `noinline` とマークされている場合、呼び出し元の関数が小さく、それ自体がコンパイラのインライン展開の候補になることに注意してください。  
  
```  
class X {  
   __declspec(noinline) int mbrfunc() {  
      return 0;   
   }   // will not inline  
};  
```  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [inline、\_\_inline、\_\_forceinline](../misc/inline-inline-forceinline.md)