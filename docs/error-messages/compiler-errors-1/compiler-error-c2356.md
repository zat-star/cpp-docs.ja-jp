---
title: "コンパイラ エラー C2356 | Microsoft Docs"
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
  - "C2356"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2356"
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2356
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

初期化セグメントは翻訳単位の間で変更することはできません。  
  
 以下の原因が考えられます。  
  
-   `#pragma init_seg` の前にセグメントの初期化コードがある。  
  
-   `#pragma init_seg` の前に別の `#pragma init_seg` がある。  
  
 解決するには、セグメントの初期化コードをモジュールの先頭に移動してください。  複数の領域を初期化する必要がある場合は、それらの領域を個別のモジュールに入れてください。  
  
 次の例では警告 C2356 が生成されます。  
  
```  
// C2356.cpp  
#pragma warning(disable : 4075)  
  
int __cdecl myexit(void (__cdecl *)());  
int __cdecl myexit2(void (__cdecl *)());  
  
#pragma init_seg(".mine$m",myexit)  
#pragma init_seg(".mine$m",myexit2)   // C2356  
```