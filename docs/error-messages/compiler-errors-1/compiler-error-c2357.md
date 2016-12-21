---
title: "コンパイラ エラー C2357 | Microsoft Docs"
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
  - "C2357"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2357"
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2357
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'type' 型の関数である必要があります。  
  
 宣言した `atexit` 関数のバージョンが、コンパイラによって内部で宣言されたバージョンと一致しません。  `atexit` を次のように宣言してください。  
  
```  
int __cdecl atexit(void (__cdecl *)());  
```  
  
 詳細については、「[init\_seg](../../preprocessor/init-seg.md)」を参照してください。  
  
 次の例では警告 C2357 が生成されます。  
  
```  
// C2357.cpp  
// compile with: /c  
// C2357 expected  
#pragma warning(disable : 4075)  
// Uncomment the following line to resolve.  
// int __cdecl myexit(void (__cdecl *)());  
#pragma init_seg(".mine$m",myexit)  
```