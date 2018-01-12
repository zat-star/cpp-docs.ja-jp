---
title: "コンパイラ エラー C3535 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3535
dev_langs: C++
helpviewer_keywords: C3535
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5797d644ec13ed89bad3ddcda23be109df067b03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3535"></a>コンパイラ エラー C3535
'type1' から 'type2' の型を推測できません。  
  
 宣言された変数の型、`auto`キーワードは、初期化式の型から推論できません。 初期化式が評価された場合、たとえば、このエラーが発生`void`、これは、型ではありません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  初期化式の型がないことを確認`void`です。  
  
2.  宣言が基本型へのポインターでないことを確認します。 詳細については、次を参照してください。[基本的な型](../../cpp/fundamental-types-cpp.md)です。  
  
3.  宣言が、型へのポインターの場合は、初期化式、ポインター型であることを確認します。  
  
## <a name="example"></a>例  
 初期化式が評価されるため、次の例で C3535`void`です。  
  
```  
// C3535a.cpp  
// Compile with /Zc:auto  
void f(){}  
int main()  
{  
   auto x = f();   //C3535  
   return 0;  
}  
```  
  
## <a name="example"></a>例  
 ステートメントの変数を宣言するため、次の例で C3535`x`推測される型が初期化子の型へのポインターとして式をダブルクリックします。 その結果、コンパイラは、変数の型を推測できません。  
  
```  
// C3535b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto* x = 123.0;   // C3535  
   return 0;  
}  
```  
  
## <a name="example"></a>例  
 次の例では C3535 のため変数`p`推測される型へのポインターを宣言していますが、初期化式がポインター型ではありません。  
  
```  
// C3535c.cpp  
// Compile with /Zc:auto  
class A { };  
A x;  
auto *p = x;  // C3535  
```  
  
## <a name="see-also"></a>参照  
 [auto キーワード](../../cpp/auto-keyword.md)   
 [基本型](../../cpp/fundamental-types-cpp.md)