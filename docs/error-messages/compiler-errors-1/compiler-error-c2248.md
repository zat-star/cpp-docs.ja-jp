---
title: "コンパイラ エラー C2248 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2248
dev_langs:
- C++
helpviewer_keywords:
- C2248
ms.assetid: 7a3ba0e8-d3b9-4bb9-95db-81ef17e31d23
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a6023532a7644753f1aaff957232fde70d01426f
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2248"></a>コンパイラ エラー C2248
'*メンバー*': アクセスできない'*access_level*'クラスで宣言されたメンバー'*クラス*'  
  
派生クラスのメンバーにアクセスできない`private`基底クラスのメンバーです。 アクセスすることはできません`private`または`protected`クラスのインスタンスのメンバーです。  
  
## <a name="example"></a>例  
  
クラスのプロテクト メンバーは、クラスの外部からアクセスまたは次の例は、プライベートと C2248 を生成します。 この問題を解決するには、クラスの外部に直接これらのメンバーはアクセスしません。 パブリック メンバーのデータとメンバー関数を使用して、クラスとやり取りします。  
  
```cpp  
// C2248_access.cpp 
// compile with: cl /EHsc /W4 C2248_access.cpp 
#include <stdio.h>  

class X {  
public:  
    int  m_publicMember;  
    void setPrivateMember( int i ) {  
        m_privateMember = i;  
        printf_s("\n%d", m_privateMember);  
    }  
protected:  
    int  m_protectedMember;  
  
private:  
    int  m_privateMember;  
} x;  
  
int main() {  
    x.m_publicMember = 4;  
    printf_s("\n%d", x.m_publicMember);  
    x.m_protectedMember = 2; // C2248 m_protectedMember is protected  
    x.m_privateMember = 3;   // C2248  m_privMemb is private  
    x.setPrivateMember(0);   // OK uses public access function  
}  
```  
  
C2248 準拠の問題は、テンプレートのフレンドと特殊化の使用です。 この問題を解決するには、テンプレート関数フレンドを宣言、空のテンプレート パラメーター リスト <> または特定のテンプレート パラメーターを使用します。  
  
```cpp  
// C2248_template.cpp 
// compile with: cl /EHsc /W4 C2248_template.cpp 
template<class T>  
void f(T t) {  
    t.i;   // C2248  
}  
  
struct S {  
private:  
    int i;  
  
public:  
    S() {}  
    friend void f(S);   // refer to the non-template function void f(S)  
    // To fix, comment out the previous line and
    // uncomment the following line.  
    // friend void f<S>(S);  
};  
  
int main() {  
    S s;  
    f<S>(s);  
}  
```  
  
C2248 準拠の問題は、クラスがクラスのスコープ内のフレンド宣言に表示されない場合とクラスのフレンドを宣言しようとする場合です。 この問題を解決するには、外側のクラスへのフレンド関係を付与します。  
  
```cpp  
// C2248_enclose.cpp  
// compile with: cl /W4 /c C2248_enclose.cpp  
class T {  
    class S {  
        class E {};  
    };  
    friend class S::E;   // C2248  
};  
  
class A {  
    class S {  
        class E {};  
        friend class A;  // grant friendship to enclosing class  
    };  
    friend class S::E;   // OK  
};  
```
