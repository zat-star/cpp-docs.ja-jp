---
title: "コンパイラの警告 (レベル 4) C4336 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4336"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4336"
ms.assetid: 93f199dd-d6dd-42c0-82d8-c12d101a7235
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラの警告 (レベル 4) C4336
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

相互参照したタイプ ライブラリ 'type\_lib1' をインポートしてから、'type\_lib2' をインポートします。  
  
 タイプ ライブラリが [\#import](../Topic/%23import%20Directive%20\(C++\).md) ディレクティブで参照されました。  一方、タイプ ライブラリには、`#import` で参照されていない別のタイプ ライブラリへの参照が含まれていました。  この別の .tlb ファイルがコンパイラによって見つかりました。  
  
 次の 2 つのファイルから作成された \(midl.exe でコンパイルされた\) 2 つのタイプ ライブラリがディスクにあるとします。  
  
```  
// c4336a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library c4336aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C4336  
   {  
      one, two, three  
   };  
};  
```  
  
 2 つ目のタイプ ライブラリは次のとおりです。  
  
```  
// c4336b.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
library C4336bLib  
{  
   importlib ("c4336a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
   struct S_C4336  
   {  
      enum E_C4336 e;  
   };  
};  
```  
  
 次の例では警告 C4336 が生成されます。  
  
```  
// C4336.cpp  
// compile with: /W4 /LD  
// #import "C4336a.tlb"  
#import "C4336b.tlb"   // C4336, uncomment previous line to resolve  
```