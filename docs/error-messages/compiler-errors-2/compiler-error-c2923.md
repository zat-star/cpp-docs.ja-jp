---
title: "コンパイラ エラー C2923 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2923
dev_langs:
- C++
helpviewer_keywords:
- C2923
ms.assetid: 6b92933b-13ef-4124-99d9-b89f9fdae030
caps.latest.revision: 11
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 62068119ea345a8df30bd0e23384016801ee0857
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2923"></a>コンパイラ エラー C2923
'type': 'identifier' は、パラメーター 'param' の有効なテンプレート型引数ではありません  
  
 引数リストに、テンプレートまたはジェネリックのインスタンス化に必要な型がありません。 テンプレート宣言またはジェネリック宣言を確認してください。  
  
 次の例では C2923 が生成されます。  
  
```  
// C2923.cpp  
template <class T> struct TC {};  
int x;  
int main() {  
   TC<x>* tc2;   // C2923  
   TC<int>* tc2;   // OK  
}  
```  
  
 C2923 は、ジェネリックを使用しているときも発生します。  
  
```  
// C2923b.cpp  
// compile with: /clr /c  
generic <class T> ref struct GC {};  
  
int x;  
  
int main() {  
   GC<x>^ gc2;   // C2923  
   GC<int>^ gc2;   // OK  
}  
```
