---
title: "コンパイラ エラー C2341 | Microsoft Docs"
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
  - "C2341"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2341"
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2341
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'section name' : セグメントは data\_seg か code\_seg プラグマを使って定義する必要があります。  
  
 [allocate](../Topic/allocate.md) ステートメントが参照しているセグメントは、[code\_seg](../../preprocessor/code-seg.md)、[data\_seg](../../preprocessor/data-seg.md)、または [section](../../preprocessor/section.md) の各プラグマでまだ定義されていません。  
  
 次の例では警告 C2341 が生成されます。  
  
```  
// C2341.cpp  
// compile with: /c  
__declspec(allocate(".test"))   // C2341  
int j = 1;  
```  
  
 解決方法 :  
  
```  
// C2341b.cpp  
// compile with: /c  
#pragma data_seg(".test")  
__declspec(allocate(".test"))  
int j = 1;  
```