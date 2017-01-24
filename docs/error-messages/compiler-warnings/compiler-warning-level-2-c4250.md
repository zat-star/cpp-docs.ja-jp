---
title: "コンパイラの警告 (レベル 2) C4250 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4250"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4250"
ms.assetid: d47f7249-6b5a-414b-b2d4-56e5d246a782
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 2) C4250
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class1' : 2 つ以上のメンバーが同じ名前を持っています。'class2::member' から継承します。  
  
 2 つ以上のメンバーが同じ名前を持っています。  `class2` はこのメンバーを持つほかのクラスの基本クラスであるため、class2 のメンバーが継承されます。  
  
 C4250 が表示されないようにするには、[warning](../../preprocessor/warning.md) プラグマを使用します。  
  
 仮想基本クラスは複数の派生クラスで共有されるので、派生クラス内の名前の方が、基本クラス内の名前よりも優先度が高くなります。  たとえば、次のクラス階層の場合、diamond: 内で継承される func 定義には、weak クラスから得られる vbc::func\(\) インスタンスと、dominant クラスから得られる dominant::func\(\) インスタンスの 2 つがあります。  diamond クラス オブジェクトを通じて func\(\) を非限定呼び出しすると、常に dominate::func\(\) インスタンスが呼び出されます。weak クラスが func\(\) のインスタンスを導入する場合は、どちらの定義も優先されず、呼び出しにあいまいであるとしてフラグが設定されます。  
  
```  
// C4250.cpp  
// compile with: /c /W2  
#include <stdio.h>  
struct vbc {  
   virtual void func() { printf("vbc::func\n"); }  
};  
  
struct weak : public virtual vbc {};  
  
struct dominant : public virtual vbc {  
   void func() { printf("dominant::func\n"); }  
};  
  
struct diamond : public weak, public dominant {};  
  
int main() {  
   diamond d;  
   d.func();   // C4250  
}  
```  
  
## 使用例  
 次の例では C4250 エラーが生成されます。  
  
```  
// C4250_b.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
using namespace std;  
class A {  
public:  
   virtual operator int () {  
      return 2;  
   }  
};  
  
class B : virtual public A {  
public:  
   virtual operator int () {  
      return 3;  
   }  
};  
  
class C : virtual public A {};  
  
class E : public B, public C {};   // C4250  
  
int main() {  
   E eObject;  
   cout << eObject.operator int() << endl;  
}  
```  
  
## 使用例  
 この例では、より複雑な状況を示します。  次の例では C4250 エラーが生成されます。  
  
```  
// C4250_c.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
using namespace std;  
  
class V {  
public:  
   virtual int f() {  
      return 1024;  
   }  
};  
  
class B : virtual public V {  
public:  
   int b() {  
      return f(); // B::b() calls V::f()  
   }  
};  
  
class M : virtual public V {  
public:  
   int f() {  
      return 7;  
   }  
};  
  
// because of dominance, f() is M::f() inside D,  
// changing the meaning of B::b's f() call inside a D  
class D : public B, public M {};   // C4250  
  
int main() {  
   D d;  
   cout << "value is: " << d.b();   // invokes M::f()  
}  
```