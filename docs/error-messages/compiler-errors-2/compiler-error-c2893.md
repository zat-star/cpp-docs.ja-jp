---
title: "コンパイラ エラー C2893 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2893
dev_langs:
- C++
helpviewer_keywords:
- C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6ad558968720a13b95fecc6860df5826b47874aa
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2893"></a>コンパイラ エラー C2893
関数テンプレート 'テンプレート名' の特定に失敗しました  
  
 コンパイラは関数テンプレートを特殊化に失敗しました。 このエラーの多くの原因があります。  
  
 一般に、C2893 エラーを解決する方法を関数のシグネチャを確認し、すべての型のインスタンスを作成できるかどうかを確認します。  
  
## <a name="example"></a>例  
 C2893 が原因で発生`f`のテンプレート パラメーター`T`があると推測`std::map<int,int>`が`std::map<int,int>`メンバーを持たない`data_type`(`T::data_type`でインスタンス化することができない`T = std::map<int,int>`。)。 次の例では、C2893 を生成します。  
  
```  
// C2893.cpp  
// compile with: /c /EHsc  
#include<map>  
using namespace std;  
class MyClass {};  
  
template<class T>   
inline typename T::data_type  
// try the following line instead  
// inline typename  T::mapped_type  
f(T const& p1, MyClass const& p2);  
  
template<class T>  
void bar(T const& p1) {  
    MyClass r;  
    f(p1,r);   // C2893  
}  
  
int main() {  
   map<int,int> m;  
   bar(m);  
}  
```
