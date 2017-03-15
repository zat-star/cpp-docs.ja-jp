---
title: "ユーザー定義の演算子 (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ユーザー定義の演算子 (/clr の)"
ms.assetid: 42f93b4a-6de4-4e34-b07b-5a62ac014f2c
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ユーザー定義の演算子 (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

マネージ型のユーザー定義演算子は静的メンバーまたはインスタンス メンバーとして、またはグローバル スコープで使用できます。  ただし、静的な演算子だけ Visual C\+\+ 以外の言語で作成されたクライアントからメタデータにアクセスできます。  
  
 参照型では、静的なユーザー定義演算子のパラメーターの 1 つが、これらの 1 にする必要があります:  
  
-   外側の型のインスタンスへの`type` ハンドル \(^\)。  
  
-   外側の型のインスタンスに対するハンドルへの参照型の間接参照 \(`type`^& または type^%\)。  
  
 値型の場合は、静的なユーザー定義演算子のパラメーターの 1 つが、これらの 1 にする必要があります:  
  
-   外側の値型と同じ型。  
  
-   外側の型へのポインター型の間接`type` \(^\)。  
  
-   外側の型の参照型の間接参照 \(`type`%または `type`&\)。  
  
-   ハンドルへの参照型の間接参照 \(`type`^% または `type`^&\)。  
  
 次の演算子を定義する:  
  
|演算子|単項とバイナリ形式か。|  
|---------|-----------------|  
|\!|単項|  
|\!\=|Binary|  
|%|Binary|  
|&|単項演算子および 2 項演算子|  
|&&|Binary|  
|\*|単項演算子および 2 項演算子|  
|\+|単項演算子および 2 項演算子|  
|\+\+|単項|  
|,|Binary|  
|\-|単項演算子および 2 項演算子|  
|\-\-|単項|  
|\-\>|単項|  
|\/|Binary|  
|\<|Binary|  
|\<\<|Binary|  
|\<\=|Binary|  
|\=|Binary|  
|\=\=|Binary|  
|\>|Binary|  
|\>\=|Binary|  
|\>\>|Binary|  
|^|Binary|  
|false|単項|  
|true|単項|  
|&#124;|Binary|  
|&#124;&#124;|Binary|  
|~|単項|  
  
## 使用例  
  
```  
// mcppv2_user-defined_operators.cpp  
// compile with: /clr  
using namespace System;  
public ref struct X {  
   X(int i) : m_i(i) {}  
   X() {}  
  
   int m_i;  
  
   // static, binary, user-defined operator  
   static X ^ operator + (X^ me, int i) {  
      return (gcnew X(me -> m_i + i));  
   }  
  
   // instance, binary, user-defined operator  
   X^ operator -( int i ) {  
      return gcnew X(this->m_i - i);  
   }  
  
   // instance, unary, user-defined pre-increment operator  
   X^ operator ++() {  
      return gcnew X(this->m_i++);  
   }  
  
   // instance, unary, user-defined post-increment operator  
   X^ operator ++(int i) {  
      return gcnew X(this->m_i++);  
   }  
  
   // static, unary user-defined pre- and post-increment operator  
   static X^ operator-- (X^ me) {  
      return (gcnew X(me -> m_i - 1));  
   }  
};  
  
int main() {  
   X ^hX = gcnew X(-5);  
   System::Console::WriteLine(hX -> m_i);  
  
   hX = hX + 1;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX = hX - (-1);  
   System::Console::WriteLine(hX -> m_i);  
  
   ++hX;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX++;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX--;  
   System::Console::WriteLine(hX -> m_i);  
  
   --hX;  
   System::Console::WriteLine(hX -> m_i);  
}  
```  
  
  **\-5**  
**\-4**  
**\-3**  
**\-2**  
**\-1**  
**\-2**  
**\-3**   
## 使用例  
 次の例では、コンパイルに **\/clr** を使用するときにのみ使用できる演算子の統合を示します。  演算子の統合は、代入演算子の左側には CLR 型の位置に 1 が定義されていない場合、二項演算子の割り当てのフォームを作成します。  
  
```  
// mcppv2_user-defined_operators_2.cpp  
// compile with: /clr  
ref struct A {  
   A(int n) : m_n(n) {};  
   static A^ operator + (A^ r1, A^ r2) {  
      return gcnew A( r1->m_n + r2->m_n);  
   };  
   int m_n;  
};  
  
int main() {  
   A^ a1 = gcnew A(10);  
   A^ a2 = gcnew A(20);  
  
   a1 += a2;   // a1 = a1 + a2   += not defined in source  
   System::Console::WriteLine(a1->m_n);  
}  
```  
  
  **30**   
## 参照  
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)