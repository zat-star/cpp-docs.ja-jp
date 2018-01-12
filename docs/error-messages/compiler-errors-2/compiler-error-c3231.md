---
title: "コンパイラ エラー C3231 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3231
dev_langs: C++
helpviewer_keywords: C3231
ms.assetid: fe5dc352-e634-45fa-9534-3da176294c98
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 284f92378c52475e23f0ddf9f206d6a143f3091f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3231"></a>コンパイラ エラー C3231
'arg': テンプレート型引数はジェネリック型パラメーターを使用できません  
  
 テンプレートはコンパイル時にインスタンス化されますが、ジェネリックは実行時にインスタンス化されます。 したがって、ジェネリック型が最終的に確定する実行時にテンプレートをインスタンス化することはできないため、テンプレートを呼び出せるジェネリック コードを生成することができません。  
  
 次の例では、C3231 が生成されます。  
  
```  
// C3231.cpp  
// compile with: /clr /LD  
template <class T> class A;  
  
generic <class T>  
ref class C {  
   void f() {  
      A<T> a;   // C3231  
   }  
};  
```