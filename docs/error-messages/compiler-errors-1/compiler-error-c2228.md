---
title: "コンパイラ エラー C2228 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2228
dev_langs:
- C++
helpviewer_keywords:
- C2228
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6960d2a34a6a68925e04e0812730025d1ce2ff92
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2228"></a>コンパイラ エラー C2228
'.identifier' の左側はクラス、構造体、共用体でなければなりません  
  
 ピリオド (.) の左側のオペランドはクラス、構造体、または共用体ではありません。  
  
 次の例では C2228 が生成されます。  
  
```  
// C2228.cpp  
int i;  
struct S {  
public:  
    int member;  
} s, *ps = &s;  
  
int main() {  
   i.member = 0;   // C2228 i is not a class type  
   ps.member = 0;  // C2228 ps is a pointer to a structure  
  
   s.member = 0;   // s is a structure type  
   ps->member = 0; // ps points to a structure S  
}  
```  
  
 マネージ拡張を使用する際に、間違った構文を使用した場合も、このエラーが表示されます。 他の Visual Studio の言語ではドット演算子を使用してマネージ クラスのメンバーにアクセスできますが、C++ でのオブジェクトへのポインターは、-> 演算子を使用してメンバーにアクセスする必要があることを意味します。  
  
 誤: `String * myString = checkedListBox1->CheckedItems->Item[0].ToString();`  
  
 正: `String * myString = checkedListBox1->CheckedItems->Item[0]->ToString();`
