---
title: "コンパイラの警告 (レベル 4) C4337 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4337"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4337"
ms.assetid: 70bc72d9-aac5-45cd-abd3-ebe42a05897b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 4) C4337
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

クロスレファレンスしたタイプ ライブラリ 'typelib1' \('typelib2' 内\) は自動的にインポートされています。  
  
 [\#import ディレクティブ](../Topic/%23import%20Directive%20\(C++\).md)の auto\_search 属性により、タイプ ライブラリが暗黙的にインポートされました。  
  
 次の 2 つのファイルから作成された \(midl.exe でコンパイルされた\) 2 つのタイプ ライブラリがディスクにあるとします。  
  
```  
// C4337a.idl  
[  
  uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12B)  
]  
library C4337aLib  
{  
   [uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12C)]  
   enum E_C4337a  
   {  
      one = 0,  
      two = 1,  
      three = 2  
    };  
};  
```  
  
 さらに、次の 2 番目の .idl ファイルがあります。  
  
```  
// C4337b.idl  
[  
   uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12D)  
]  
  
library C4337bLib  
{  
   importlib("c4337a.tlb");  
  
   [uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12E)]  
   struct S_C4337b  
   {  
      enum E_C4337a e;  
   };  
};  
```  
  
 次の例では警告 C4337 が生成されます。  
  
```  
// C4337.cpp  
// compile with: /W4 /LD  
#import "c4337b.tlb" auto_search   // C4337  
// explicitly #import all type libraries to resolve  
// #import "C4337a.tlb"  
// #import "C4337b.tlb"  
```