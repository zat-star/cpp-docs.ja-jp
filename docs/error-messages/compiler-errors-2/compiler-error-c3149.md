---
title: "コンパイラ エラー C3149 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3149
dev_langs:
- C++
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: dc5abf02a3210ca3d7bd858662e0c02d4f42d75d
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3149"></a>コンパイラ エラー C3149
'type': トップレベル 'char' せずに、この型をここでは使用できません  
  
 宣言が正しく指定されていません。  
  
 たとえば、可能性がありますグローバル スコープでの CLR 型を定義して、定義の一部として、型の変数を作成しようとしています。 CLR 型のグローバル変数は許可されていないため、コンパイラは C3149 を生成します。  
  
 このエラーを解決するには、関数、または型の定義内の CLR 型の変数を宣言します。  
  
 次の例では、C3149 が生成されます。  
  
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
  
 次の例では、C3149 が生成されます。  
  
```  
// C3149b.cpp  
// compile with: /clr /c  
delegate int MyDelegate(const int, int);  
void Test1(MyDelegate m) {}   // C3149  
void Test2(MyDelegate ^ m) {}   // OK  
```  

