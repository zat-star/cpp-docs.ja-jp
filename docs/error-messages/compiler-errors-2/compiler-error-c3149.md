---
title: "コンパイラ エラー C3149 | Microsoft Docs"
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
  - "C3149"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3149"
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3149
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'型' : トップレベルの 'char' なしに、この型をここに使用することはできません  
  
 宣言が正しく指定されていません。  
  
 たとえば、CLR 型をグローバル スコープで定義し、その定義の一部としてその型の変数を作成しようとしている可能性があります。  CLR 型のグローバル変数は使用できないので、コンパイラは C3149 を生成します。  
  
 このエラーを解決するには、CLR 型の変数を関数内または型定義内で宣言します。  
  
 次の例では警告 C3149 が生成されます。  
  
```  
// C3149.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   // declare an array of value types   
   array< Int32 ^> IntArray;   // C3149  
   array< Int32>^ IntArray2;   // OK  
}  
```  
  
 次の例では警告 C3149 が生成されます。  
  
```  
// C3149b.cpp  
// compile with: /clr /c  
delegate int MyDelegate(const int, int);  
void Test1(MyDelegate m) {}   // C3149  
void Test2(MyDelegate ^ m) {}   // OK  
```  
  
 **C\+\+ マネージ拡張**  
  
 マネージ オブジェクトが正しく使用されていません。  
  
 次の例では警告 C3149 が生成されます。  
  
```  
// C3149c.cpp  
// compile with: /clr:oldSyntax  
__gc class A {};  
  
int main() {  
   A a = new A;   // C3149  
   A *a = new A;   // OK  
}  
```