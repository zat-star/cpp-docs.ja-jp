---
title: "__asm ブロックでの演算子の使用 | Microsoft Docs"
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
helpviewer_keywords: 
  - "__asm キーワード [C++], 演算子"
  - "角かっこ [ ]"
  - "角かっこ [ ], __asm ブロック"
  - "演算子 [C++], __asm ブロックでの使用"
  - "角かっこ [ ]"
  - "角かっこ [ ], __asm ブロック"
ms.assetid: a26ccfd4-40ae-4a61-952f-c417982aa8dd
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __asm ブロックでの演算子の使用
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 `__asm` ブロックは **\<\<** 演算子など C または C\+\+ の演算子を使用できません。  ただしのような C および MASM すると共有された演算子 \* 演算子はアセンブリ言語の演算子として解釈されます。  たとえば`__asm` ブロックの外部で角かっこ \(\)**\[入力\]** は C が配列の要素のサイズに自動的にスケーリングする配列の添字を囲むとして解釈されます。  `__asm` ブロック内ではデータ オブジェクトまたはラベル \(\)配列のバイト オフセットをスケーリングする MASM 添字演算子として表示されます。  次のコードは相違点を示しています :  
  
```  
int array[10];  
  
__asm mov array[6], bx ;  Store BX at array+6 (not scaled)  
  
array[6] = 0;         /* Store 0 at array+24 (scaled) */  
```  
  
 `array` が最初に参照はスケーリングされませんが2 番目はスケーリングします。  定数に基づくスケーリングを実行するために  **種類**  の演算子を使用できることに注意してください。  たとえば次のステートメントは同等です :  
  
```  
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24  
  
array[6] = 0;                   /* Store 0 at array + 24 */  
```  
  
 **終了 Microsoft 固有の仕様→**  
  
## 参照  
 [\_\_asm ブロックでの C または C\+\+ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)