---
title: "コンパイラの警告 (レベル 2) C4356 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4356"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4356"
ms.assetid: 3af3defe-de33-43b6-bd6c-2c2e09e34f3f
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラの警告 (レベル 2) C4356
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : 静的データ メンバーは、派生クラスを使って初期化できません。  
  
 静的データ メンバーの初期化の形式が間違っています。  コンパイラは初期化を受け入れました。  
  
 これは、Visual C\+\+ .NET 2003 コンパイラでの互換性に影響する変更点です。  
  
 すべてのバージョンの Visual C\+\+ で同じ動作をするコードを作成するには、基本クラスを通じてメンバーを初期化します。  
  
 この警告が表示されないようにするには、[warning](../../preprocessor/warning.md) プラグマを使用します。  
  
 次の例では警告 C4356 が生成されます。  
  
```  
// C4356.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
  
template <class T>  
class C {  
   static int n;  
};  
  
class D : C<int> {};  
  
int D::n = 0; // C4356  
// try the following line instead  
// int C<int>::n = 0;  
  
class A {  
public:  
   static int n;  
};  
  
class B : public A {};  
  
int B::n = 10;   // C4356  
// try the following line instead  
// int A::n = 99;  
  
int main() {  
   using namespace std;  
   cout << B::n << endl;  
}  
```