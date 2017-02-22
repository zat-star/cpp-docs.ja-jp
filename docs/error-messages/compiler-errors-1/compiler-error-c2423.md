---
title: "コンパイラ エラー C2423 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2423"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2423"
ms.assetid: 8797fb8b-b58b-4add-b6e6-2a9a3cd9084d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2423
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'number' : スケーリングが正しくありません。  
  
 インライン アセンブラー コードで、レジスタのスケーリングに 1、2、4、8 以外の数を使用しています。  
  
 次の例では警告 C2423 が生成されます。  
  
```  
// C2423.cpp  
// processor: x86  
int main() {  
   _asm {  
      lea EAX, [EAX*3]   // C2423  
      lea EAX, [EAX+EAX*2]   // OK  
   }  
}  
```