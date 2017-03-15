---
title: "ユーザー定義変換 (C++/CLI) | Microsoft Docs"
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
  - "ユーザー定義変換 [C++]"
ms.assetid: 8010fd59-2775-4e9a-a6ed-58055032d66f
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ユーザー定義変換 (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このセクションでは、変換の型の 1 つが値型または参照型の参照またはインスタンスにとユーザー定義変換 \(UDC\) について説明します。  
  
## 暗黙的なリンクと明示的な変換  
 ユーザー定義の変換が暗黙または明示的になります。UDC は変換によって情報の損失が発生する暗黙の必要があります。  それ UDC は明示的に定義する必要があります。  
  
 ネイティブ クラスのコンストラクターがネイティブ クラスへの参照型や値型を変換するために使用できます。  
  
 変換の詳細については、「[Boxing](../windows/boxing-cpp-component-extensions.md) と [標準変換](../cpp/standard-conversions.md)」を参照してください。  
  
```  
// mcpp_User_Defined_Conversions.cpp  
// compile with: /clr  
#include "stdio.h"  
ref class R;  
class N;  
  
value class V {  
   static operator V(R^) {  
      return V();  
   }  
};  
  
ref class R {  
public:  
   static operator N(R^);  
   static operator V(R^) {  
      System::Console::WriteLine("in R::operator N");  
      return V();  
   }  
};  
  
class N {  
public:  
   N(R^) {  
      printf("in N::N\n");  
   }  
};  
  
R::operator N(R^) {  
   System::Console::WriteLine("in R::operator N");  
   return N(nullptr);  
}  
  
int main() {  
   // Direct initialization:  
   R ^r2;  
   N n2(r2);   // direct initialization, calls constructor  
   static_cast<N>(r2);   // also direct initialization  
  
   R ^r3;  
   // ambiguous V::operator V(R^) and R::operator V(R^)  
   // static_cast<V>(r3);     
}  
```  
  
 **出力**  
  
  **N::N**  
**N::N**   
## 変換元演算子  
 変換元演算子は演算子は他のクラスのオブジェクトで定義されているクラスのオブジェクトを作成します。  
  
 標準 C\+\+ では変換元演算子;をサポートしません。標準 C\+\+ でコンストラクターをこの目的で使用します。  ただし、CLR を使用すると、Visual C\+\+ 提供します変換元演算子に照会する構文のサポートを入力します。  
  
 他の CLS 準拠の言語との相互運用にするには、対応する変換元演算子を使用して特定のクラスの、ユーザー定義の単項コンストラクターをラップしたい場合があります。  
  
 変換元演算子:  
  
-   静的関数で定義されます。  
  
-   暗黙的な \(精度が含まれているとき、短いに int などの精度を失わない変換の場合\) または明示的になる場合があります。  
  
-   包含クラス オブジェクトを返します。  
  
-   唯一のパラメーター型として」From 「となります。  
  
 次の例では、「の暗黙的および明示的な変換」、変換 \(UDC\) のユーザー定義の演算子です。  
  
```  
// clr_udc_convert_from.cpp  
// compile with: /clr  
value struct MyDouble {  
   double d;  
  
   MyDouble(int i) {  
      d = static_cast<double>(i);  
      System::Console::WriteLine("in constructor");  
   }  
  
   // Wrap the constructor with a convert-from operator.  
   // implicit UDC because conversion cannot lose precision  
   static operator MyDouble (int i) {  
      System::Console::WriteLine("in operator");  
      // call the constructor  
      MyDouble d(i);  
      return d;  
   }  
  
   // an explicit user-defined conversion operator  
   static explicit operator signed short int (MyDouble) {  
      return 1;  
   }  
};  
  
int main() {  
   int i = 10;  
   MyDouble md = i;  
   System::Console::WriteLine(md.d);  
  
   // using explicit user-defined conversion operator requires a cast    
   unsigned short int j = static_cast<unsigned short int>(md);  
   System::Console::WriteLine(j);  
}  
```  
  
 **出力**  
  
  **演算子**  
**コンストラクター**  
**10**  
**1**   
## 演算子に変換  
 変換演算子に演算子が他のオブジェクトに定義されているクラスのオブジェクトに変換します。  次の例では、暗黙的に、変換、ユーザー定義変換演算子示します:  
  
```  
// clr_udc_convert_to.cpp  
// compile with: /clr  
using namespace System;  
value struct MyInt {  
   Int32 i;  
  
   // convert MyInt to String^  
   static operator String^ ( MyInt val ) {  
      return val.i.ToString();  
   }  
  
   MyInt(int _i) : i(_i) {}  
};  
  
int main() {  
   MyInt mi(10);  
   String ^s = mi;  
   Console::WriteLine(s);  
}  
```  
  
 **出力**  
  
  **10** 変換演算子は、ユーザー定義変換します。通常は、なんらかの形でデータを失う変換に適しています。  変換演算子に明示的に呼び出す場合は、キャストを使用する必要があります。  
  
```  
// clr_udc_convert_to_2.cpp  
// compile with: /clr  
value struct MyDouble {  
   double d;  
   // convert MyDouble to Int32  
   static explicit operator System::Int32 ( MyDouble val ) {  
      return (int)val.d;  
   }  
};  
  
int main() {  
   MyDouble d;  
   d.d = 10.3;  
   System::Console::WriteLine(d.d);  
   int i = 0;  
   i = static_cast<int>(d);  
   System::Console::WriteLine(i);  
}  
```  
  
 **出力**  
  
  **10.3**  
**10**   
## ジェネリック クラスを変換するには  
 T.にジェネリック クラスを変換できます。  
  
```  
// clr_udc_generics.cpp  
// compile with: /clr  
generic<class T>   
public value struct V {  
   T mem;  
   static operator T(V v) {  
      return v.mem;  
   }  
  
   void f(T t) {  
      mem = t;  
   }  
};  
  
int main() {  
   V<int> v;  
   v.f(42);  
   int i = v;  
   i += v;  
   System::Console::WriteLine(i == (42 * 2) );  
}  
```  
  
 **出力**  
  
  **True** 変換コンストラクターは型を受け取り、オブジェクトを作成するために使用します。変換コンストラクターは直接初期化のみと呼ばれます; キャストは変換コンストラクターを呼び出しません。  既定で、変換コンストラクターは CLR 型に明示的になります。  
  
```  
// clr_udc_converting_constructors.cpp  
// compile with: /clr  
public ref struct R {  
   int m;  
   char c;  
  
   R(int i) : m(i) { }  
   R(char j) : c(j) { }  
};  
  
public value struct V {  
   R^ ptr;  
   int m;  
  
   V(R^ r) : ptr(r) { }  
   V(int i) : m(i) { }  
};  
  
int main() {   
   R^ r = gcnew R(5);  
  
   System::Console::WriteLine( V(5).m);  
   System::Console::WriteLine( V(r).ptr);  
}  
```  
  
 **出力**  
  
  **5**  
**R** このコード サンプルでは、暗黙の静的な変換関数は、明示的な変換のコンストラクターと同じことを実行します。  
  
```  
public value struct V {  
   int m;  
   V(int i) : m(i) {}  
   static operator V(int i) {  
      V v(i*100);  
      return v;  
   }  
};  
  
public ref struct R {  
   int m;  
   R(int i) : m(i) {}  
   static operator R^(int i) {  
      return gcnew R(i*100);  
   }  
};  
  
int main() {  
   V v(13);   // explicit  
   R^ r = gcnew R(12);   // explicit  
  
   System::Console::WriteLine(v.m);  
   System::Console::WriteLine(r->m);  
  
   // explicit ctor can't be called here: not ambiguous  
   v = 5;  
   r = 20;  
  
   System::Console::WriteLine(v.m);  
   System::Console::WriteLine(r->m);  
}  
```  
  
 **出力**  
  
  **13**  
**12**  
**500**  
**2000**   
## 参照  
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)