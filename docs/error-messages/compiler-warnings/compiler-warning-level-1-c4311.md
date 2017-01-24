---
title: "コンパイラの警告 (レベル 1) C4311 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4311"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4311"
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4311
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'変数' : ポインターを '型' から '型' へ切り詰めます。  
  
 この警告は 64 ビット ポインターの切り捨ての問題を検出します。  たとえば、コードが 64 ビット アーキテクチャ用にコンパイルされている場合、ポインターの値 \(64 ビット\) は `int` \(32 ビット\) に代入されるときに切り詰められます。  詳細については、「[ポインターの使用規則](http://msdn.microsoft.com/library/windows/desktop/aa384242)」を参照してください。  
  
 警告 C4311 が発生する一般的な原因の詳細については、「[一般的なコンパイラ エラー](http://msdn.microsoft.com/library/windows/desktop/aa384160)」を参照してください。  
  
 次のコード例では、64 ビットをターゲットとしたコンパイル時に警告 C4311 を生成し、修正する方法を示します。  
  
```  
// C4311.cpp  
// compile by using: cl /W1 C4311.cpp  
int main() {  
   void* p = &p;  
   unsigned int i = (unsigned int) p;   // C4311 for 64-bit targets  
   unsigned long long j = (unsigned long long) p;   // OK  
}  
  
```