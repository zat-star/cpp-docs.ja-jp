---
title: "コンパイラ エラー C2753 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2753
dev_langs:
- C++
helpviewer_keywords:
- C2753
ms.assetid: 92bfeeac-524a-4a8e-9a4f-fb8269055826
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: 7d77c7fa0c8035f8bb3a9ef732880bce4253c25b
ms.contentlocale: ja-jp
ms.lasthandoff: 04/24/2017

---
# <a name="compiler-error-c2753"></a>コンパイラ エラー C2753
'*テンプレート*': 部分的特殊化はプライマリ テンプレートの引数リストと一致ことはできません  
  
 テンプレート引数リストには、パラメーター リストが一致すると、コンパイラにより、同じテンプレートとして扱います。 同じテンプレートを 2 回定義することはできません。  
  
## <a name="example"></a>例
 次の例では、C2753 を生成し、その修正方法を示しています。  
  
```cpp  
// C2753.cpp  
// compile with: cl /c C2753.cpp
template<class T>  
struct A {};  
  
template<class T>  
struct A<T> {};   // C2753  
// try the following line instead  
// struct A<int> {};  
  
template<class T, class U, class V, class W, class X>  
struct B {};  
```
