---
title: "コンパイラの警告 (レベル 1) C4561 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4561"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4561"
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラの警告 (レベル 1) C4561
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\_\_fastcall' は '\/clr' スイッチとの互換性がありません : '\_\_stdcall' に変換しています。  
  
 [\_\_fastcall](../../cpp/fastcall.md) 関数呼び出し規約は、[\/clr](../../build/reference/clr-common-language-runtime-compilation.md) コンパイラ オプションとは併用できません。  `__fastcall` の呼び出しは無視されます。  この警告を解決するには、**\_\_fastcall**  の呼び出しを削除するか、**\/clr** を指定せずにコンパイルします。  
  
 次の例では警告 C4561 が生成されます。  
  
```  
// C4561.cpp  
// compile with: /clr /W1 /c  
// processor: x86  
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve  
```