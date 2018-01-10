---
title: "コンパイラ エラー C3149 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3149
dev_langs: C++
helpviewer_keywords: C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 154ae99c5e47438f6fca3b85ac8318c1b14f7a30
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
