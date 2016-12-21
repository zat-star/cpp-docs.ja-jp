---
title: "restrict | Microsoft Docs"
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
  - "restrict"
  - "restrict_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec キーワード [C++], restrict"
  - "restrict __declspec キーワード"
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# restrict
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 ポインター型を返し、関数が他のポインターでエイリアス化されないオブジェクトを返すことをコンパイラに伝える関数宣言または関数定義に適用されます。  
  
## 構文  
  
```  
__declspec(restrict) return_type f();  
```  
  
## 解説  
 コンパイラは、`__declspec(restrict)` を反映させます。  たとえば、CRT `malloc` 関数は `__declspec(restrict)` で修飾されるため、`malloc` でメモリ位置に初期化されたポインターも暗黙でエイリアスは設定されません。  
  
 コンパイラは、ポインターが実際にはエイリアス化されていないことを確認しません。  `restrict __declspec` 修飾子で示したポインターにエイリアスがないかどうか確認するのは開発者の責任です。  
  
 変数の同様のセマンティクスについては、「[\_\_restrict](../cpp/extension-restrict.md)」を参照してください。  
  
## 使用例  
 `restrict` の使用例は、「[noalias](../cpp/noalias.md)」を参照してください。  
  
 C\+\+ AMP の一部である restrict キーワードの詳細については、「[restrict \(C\+\+ AMP\)](../cpp/restrict-cpp-amp.md)」を参照してください。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)