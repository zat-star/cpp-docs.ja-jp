---
title: "コンパイラ エラー C2247 | Microsoft Docs"
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
  - "C2247"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2247"
ms.assetid: 72efa03e-615e-4ef9-aede-0a98654b20fd
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2247
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'識別子' はアクセスできません。'クラス' は '指定子' で 'クラス' からの継承で使われています。  
  
 `identifier` が、プライベートまたはプロテクトのアクセス レベルで宣言されたクラスから継承されています。  
  
 次の例では警告 C2247 が生成されます。  
  
```  
// C2247.cpp  
class A {  
public:  
   int i;  
};  
class B : private A {};    // B inherits a private A  
class C : public B {} c;   // so even though C's B is public  
int j = c.i;               // C2247, i not accessible  
```  
  
 このエラーは、プロテクト メンバーのアクセスを制御している Visual Studio .NET 2003 で行った、コンパイラ準拠作業の結果として生成されることもあります。  プロテクト メンバー \(n\) には、そのメンバー \(n\) が属するクラス \(A\) の継承クラス \(B\) のメンバー関数を通じてだけアクセスできます。  
  
 Visual Studio .NET 2003 と Visual Studio .NET の両方のバージョンの Visual C\+\+ で有効なコードを作成するには、メンバーをその型のフレンドとして宣言します。  パブリック継承も使用できます。  
  
```  
// C2247b.cpp  
// compile with: /c  
// C2247 expected  
class A {  
public:  
   void f();  
   int n;  
};  
  
class B: protected A {  
   // Uncomment the following line to resolve.  
   // friend void A::f();  
};  
  
void A::f() {  
   B b;  
   b.n;  
}  
```  
  
 C2247 は、プライベート基本クラスにはアクセスできない Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として生成されることもあります。  型 \(B\) に対するプライベート基本クラスであるクラス \(A\) は、B を基本クラスとして使用する型 \(C\) からアクセスできません。  
  
 Visual Studio .NET 2003 と Visual Studio .NET の両方のバージョンの Visual C\+\+ で有効なコードを作成するには、スコープ演算子を使用します。  
  
```  
// C2247c.cpp  
// compile with: /c  
struct A {};  
  
struct B: private A {};  
  
struct C : B {  
   void f() {  
      A *p1 = (A*) this;   // C2247  
      // try the following line instead  
      // ::A *p2 = (::A*) this;  
   }  
};  
```