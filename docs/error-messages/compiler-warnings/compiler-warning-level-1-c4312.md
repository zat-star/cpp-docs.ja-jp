---
title: "コンパイラの警告 (レベル 1) C4312 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4312"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4312"
ms.assetid: 541906ed-4f62-4bcb-947f-cf9ae7411bcb
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラの警告 (レベル 1) C4312
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'操作' :  'type1' からより大きいサイズの 'type2' へ変換します。  
  
 この警告は、32 ビット値を 64 ビット ポインター型に割り当てようとしたことを検出します。たとえば、32 ビット `int` または `long` を 64 ビット ポインターにキャストした場合などです。  
  
 この変換は、符号拡張が発生する場合、32 ビットに収まるポインター値であっても安全でないことがあります。  負の 32 ビット整数が 64 ビット ポインター型に割り当てられる場合、符号拡張によって、ポインター値が整数の値とは異なるメモリ アドレスを参照するようになります。  
  
 この警告は、64 ビット コンパイル ターゲットに対してのみ発行されます。  詳細については、「[ポインターの使用規則](http://msdn.microsoft.com/library/windows/desktop/aa384242)」を参照してください。  
  
 次のコード例は、64 ビットのターゲットのコンパイル時に C4312 を生成します。  
  
```  
// C4312.cpp  
// compile by using: cl /W1 /LD C4312.cpp  
void* f(int i) {  
   return (void*)i;   // C4312 for 64-bit targets  
}  
  
void* f2(__int64 i) {  
   return (void*)i;   // OK  
}  
```