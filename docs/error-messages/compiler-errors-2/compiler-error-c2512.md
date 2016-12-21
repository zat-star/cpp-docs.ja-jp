---
title: "コンパイラ エラー C2512 | Microsoft Docs"
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
  - "C2512"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2512"
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2512
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : クラス、構造体、共用体に既定のコンストラクターがありません。  
  
 指定したクラス、構造体、または共用体で使用可能な既定のコンストラクターがありません。  ユーザー定義のコンストラクターが指定されていない場合のみ、コンパイラによって既定のコンストラクターが提供されます。  
  
 非 void 型のパラメーターを受け取るコンストラクターを指定して、クラスをパラメーターなしで作成できるようにする場合 \(配列の要素として作成する場合など\)、既定のコンストラクターも指定する必要があります。  既定のコンストラクターには、すべてのパラメーターに既定値を使用したコンストラクターを指定できます。  
  
 次の例では、C2512 を生成し、その修正方法を示しています。  
  
```  
// C2512.cpp  
// C2512 expected  
struct B {  
   B (char *);  
   // Uncomment the following line to fix.  
   // B() {};  
};  
  
int main() {  
   B b;   
}  
```  
  
 次の例では、少し複雑な C2512 を示します。  このエラーを修正するには、クラスを定義してからそのコンストラクターを参照するようにコードを再配置します。  
  
```  
// C2512b.cpp  
// compile with: /c  
struct S {  
   struct X;  
  
   void f() {  
      X *x = new X();   // C2512 X not defined yet  
   }  
  
};  
  
struct S::X {};  
  
struct T {  
   struct X;  
   void f();  
};  
  
struct T::X {};  
  
void T::f() {  
   X *x = new X();  
}  
```  
  
 C2512 は、const または参照データ メンバーを含むクラスの既定のコンストラクターへの呼び出しによっても発生することがあります。  これらのメンバーは、コンストラクターの初期化子リスト内で初期化する必要があります。これにより、コンパイラは既定のコンストラクターを生成できなくなります。  
  
 次の例では、C2512 を生成し、その修正方法を示しています。  
  
```  
// C2512c.cpp  
// Compile by using: cl /c /W3 C2512c.cpp  
struct S {  
   const int i_;  
   int &r_;   
};   
  
int SumS() {  
   const int ci = 7;  
   int ir = 42;  
  
   S s1; // C2512 - no default constructor available  
   S s2{ci, ir};  // Fix - initialize const and reference members   
   return s2.i_ + s2.r_;  
}  
```