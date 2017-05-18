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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 3e1a7fb29d792a5b72c2f6b67021c134c224bac2
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2228"></a>コンパイラ エラー C2228
'.identifier' の左側はクラス、構造体、共用体でなければなりません  
  
 ピリオド (.) の左側のオペランドはクラス、構造体または共用体ではありません。  
  
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
  
 正しくありません。`String * myString = checkedListBox1->CheckedItems->Item[0].ToString();`  
  
 そうです：`String * myString = checkedListBox1->CheckedItems->Item[0]->ToString();`
