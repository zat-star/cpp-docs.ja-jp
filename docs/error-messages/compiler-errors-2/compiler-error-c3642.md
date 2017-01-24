---
title: "コンパイラ エラー C3642 | Microsoft Docs"
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
  - "C3642"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3642"
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3642
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'return\_type\/args' : \_\_clrcall 呼び出し規約を伴う関数を、ネイティブ コードから呼び出すことはできません  
  
 [\_\_clrcall](../../cpp/clrcall.md) 呼び出し規約でマークされている関数をネイティブ \(アンマネージ\) コードから呼び出すことはできません。  
  
 *return\_type\/args* は 関数名や、呼び出そうとしている `__clrcall` 関数の型です。関数ポインターから呼び出す場合は型が使用されます。  
  
 ネイティブ コンテキストからマネージ関数を呼び出すには、`__clrcall` 関数を呼び出す "ラッパー" 関数を追加できます。  または、CLR マーシャリング機構を使用します。詳細については、「[方法: PInvoke を使用して関数ポインターをマーシャリングする](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)」を参照してください。  
  
 次の例では警告 C3642 が生成されます。  
  
```  
// C3642.cpp  
// compile with: /clr  
using namespace System;  
struct S {  
   void Test(String ^ s) {   // CLR type in signature, implicitly __clrcall  
      Console::WriteLine(s);  
   }  
   void Test2(char * s) {  
      Test(gcnew String(s));  
   }  
};  
  
#pragma unmanaged  
int main() {  
   S s;  
   s.Test("abc");   // C3642  
   s.Test2("abc");   // OK  
}  
```