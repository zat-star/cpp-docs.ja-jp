---
title: "プロトタイプ宣言されていない関数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 34200b8c-5b52-4f0d-aff8-9f70d82868ed
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# プロトタイプ宣言されていない関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

完全にプロトタイプ宣言されていない関数の場合、呼び出し元は整数値を整数として、浮動小数点値を倍精度として渡します。  浮動小数点値だけの場合、呼び出し先の整数レジスタに float 型の値を渡す必要があるときには、整数レジスタと浮動小数点レジスタの両方に float 型の値が含まれます。  
  
```  
func1();  
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7  
   func1(2, 1.0, 7);  
}  
```  
  
## 参照  
 [呼び出し規約](../build/calling-convention.md)