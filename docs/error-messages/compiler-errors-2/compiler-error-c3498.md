---
title: "Compiler Error C3498 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3498"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3498"
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compiler Error C3498
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': マネージ型または WinRT 型を持つ変数のキャプチャはできません  
  
 ラムダで、マネージ型または Windows ランタイム型を持つ変数をキャプチャすることはできません。  
  
### このエラーを解決するには  
  
-   マネージ変数または Windows ランタイム変数をラムダ式のパラメーター リストに渡します。  
  
## 使用例  
 次の例では、マネージ型を持つ変数がラムダ式のキャプチャ リストに表示されるため、C3498 が生成されます。  
  
```  
// C3498a.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String ^ s = "Hello";  
   [&s](String ^ r)   
      { return String::Concat(s, r); } (", World!"); // C3498  
}  
```  
  
## 使用例  
 次の例では、マネージ型の変数 `s` をラムダ式のパラメーター リストに渡すことにより、C3498 を解決します。  
  
```  
// C3498b.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String ^ s = "Hello";  
   [](String ^ s, String ^ r)   
      { return String::Concat(s, r); } (s, ", World!");  
}  
```  
  
## 参照  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)