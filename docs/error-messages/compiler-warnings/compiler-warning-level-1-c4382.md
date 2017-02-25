---
title: "コンパイラの警告 (レベル 1) C4382 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4382"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4382"
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 1) C4382
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

type' をスローします : \_\_clrcall デストラクターを伴う型、またはコピー コンストラクターは \/clr:pure モジュールでのみキャッチできます  
  
 **\/clr:pure** ではなく **\/clr** を指定してコンパイルした場合、例外処理はネイティブ型のメンバー関数が [\_\_clrcall](../../cpp/clrcall.md) ではなく [\_\_cdecl](../Topic/__cdecl.md) になることを要求します。  `__clrcall` 呼び出し規約を使用するメンバー関数を持つネイティブ型は、**\/clr** を指定してコンパイルされたモジュール内でキャッチできません。  
  
 **\/clr:pure** を指定してコンパイルされたモジュール内で例外がキャッチされた場合は、この警告を無視できます。  
  
 詳細については、「[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
## 使用例  
 次の例では C4382 エラーが生成されます。  
  
```  
// C4382.cpp  
// compile with: /clr /W1 /c  
struct S {  
   __clrcall ~S() {}  
};  
  
struct T {  
   ~T() {}  
};  
  
int main() {  
   S s;  
   throw s;   // C4382  
  
   S * ps = &s;  
   throw ps;   // OK  
  
   T t;  
   throw t;   // OK  
}  
```