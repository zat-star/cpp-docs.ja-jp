---
title: "コンパイラ エラー C2248 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2248"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2248"
ms.assetid: 7a3ba0e8-d3b9-4bb9-95db-81ef17e31d23
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# コンパイラ エラー C2248
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'メンバー' : 'access' メンバー \(クラス 'クラス' で宣言されている\) にアクセスできません  
  
 派生クラスのメンバーは、基本クラスの `private` メンバーにアクセスできません。  クラスのインスタンスの `private` メンバーまたは `protected` メンバーにアクセスできません。  
  
 C2248 の詳細については、サポート技術情報の文書 \(KB243351\) を参照してください。  
  
 次の例では警告 C2248 が生成されます。  
  
```  
// C2248.cpp  
#include <stdio.h>  
class X {  
public:  
   int  m_pubMemb;  
   void setPrivMemb( int i ) {  
      m_privMemb = i;  
      printf_s("\n%d", m_privMemb);  
   }  
protected:  
   int  m_protMemb;  
  
private:  
   int  m_privMemb;  
} x;  
  
int main() {  
   x.m_pubMemb = 4;  
   printf_s("\n%d", x.m_pubMemb);  
   x.m_protMemb = 2;   // C2248 m_protMemb is protected  
   x.m_privMemb = 3;   // C2248  m_privMemb is private  
   x.setPrivMemb(0);   // OK uses public access function  
}  
```  
  
 テンプレートのフレンドおよび特殊な形式を使用すると、準拠の問題により C2248 が発生します。  詳細については、「[リンカー ツール エラー LNK2019](../Topic/Linker%20Tools%20Error%20LNK2019.md)」を参照してください。  
  
```  
// C2248_b.cpp  
template<class T>  
void f(T t) {  
   t.i;   // C2248  
}  
  
struct S {  
private:  
   int i;  
  
public:  
   S() {}  
   // Delete the following line to resolve.  
   friend void f(S);   // refer to the non-template function void f(S)  
  
   // Uncomment the following line to resolve.  
   // friend void f<S>(S);  
};  
  
int main() {  
   S s;  
   f<S>(s);  
}  
```  
  
 クラスのフレンドを宣言しようとした場合に、そのクラスがクラスのスコープ内のフレンド宣言から参照できない場合も、準拠の問題により C2248 が発生します。  この場合のエラーを解決するには、フレンド宣言の外側のクラスにフレンドシップを与えます。  
  
```  
// C2248_c.cpp  
// compile with: /c  
class T {  
   class S {  
      class E {};  
   };  
   friend class S::E;   // C2248  
};  
  
class A {  
   class S {  
      class E {};  
      friend class A;   // grant friendship to enclosing class  
   };  
   friend class S::E;   // OK  
};  
```