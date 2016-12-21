---
title: "コンパイラ エラー C2660 | Microsoft Docs"
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
  - "C2660"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2660"
ms.assetid: 2e01a1db-4f00-4df6-a04d-cb6f70a6922b
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2660
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 関数に number 個のパラメーターを指定することはできません。  
  
 関数の呼び出しに指定されたパラメーターの数が間違っています。  
  
 MFC メンバー関数ではなく同じ名前の Windows API 関数を誤って呼び出すと、C2660 が発生します。  この問題を解決する方法は次のとおりです。  
  
-   メンバー関数の呼び出し形式に合うように関数呼び出しを書き直します。  
  
-   スコープ解決演算子 \(`::`\) を使用して、グローバルな名前空間で関数名を検索するようにコンパイラに通知します。  
  
## 使用例  
 次の例では C2660 エラーが生成されます。  
  
```  
// C2660.cpp  
void func( int, int ) {}  
  
int main() {  
   func( 1 );   // C2660 func( int ) not declared  
   func( 1, 0 );   // OK  
}  
```  
  
## 使用例  
 C2660 エラーは、マネージ型の Dispose メソッドを直接呼び出す場合にも発生することがあります。  詳細については、「[デストラクターとファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)」を参照してください。  次の例では C2660 エラーが生成されます。  
  
```  
// C2660_a.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Threading;  
  
void CheckStatus( Object^ stateInfo ) {}  
  
int main() {  
   ManualResetEvent^ event = gcnew ManualResetEvent( false );     
   TimerCallback^ timerDelegate = gcnew TimerCallback( &CheckStatus );  
   Timer^ stateTimer = gcnew Timer( timerDelegate, event, 1000, 250 );  
  
   stateTimer->Dispose();   // C2660  
   stateTimer->~Timer();   // OK  
}  
```  
  
## 使用例  
 派生クラスによって関数が隠ぺいされると、C2660 が発生します。  
  
```  
// C2660b.cpp  
// C2660 expected  
#include <stdio.h>  
  
class f {  
public:  
   void bar() {  
      printf_s("in f::bar\n");  
    }  
};  
  
class f2 : public f {  
public:  
   void bar(int i){printf("in f2::bar\n");}  
   // Uncomment the following line to resolve.  
   // using f::bar;   // - using declaration added  
   // or  
   // void bar(){__super::bar();}  
};  
  
int main() {  
   f2 fObject;  
   fObject.bar();  
}  
```  
  
## 使用例  
 インデックス付きプロパティの呼び出しを正しく行わないと、C2660 が発生します。  
  
```  
// C2660c.cpp  
// compile with: /clr  
ref class X {  
   double d;  
public:  
   X() : d(1.9) {}  
   property double MyProp[] {  
      double get(int i) {  
         return d;  
      }  
   }   // end MyProp definition  
};  
  
int main() {  
   X ^ MyX = gcnew X();  
   System::Console::WriteLine(MyX->MyProp(1));   // C2660  
   System::Console::WriteLine(MyX->MyProp[1]);   // OK  
}  
```  
  
## 使用例  
 インデックス付きプロパティの呼び出しを正しく行わないと、C2660 が発生します。  
  
```  
// C2660d.cpp  
// compile with: /clr  
ref class A{  
public:  
   property int default[int,int] {  
      int get(int a, int b) {  
         return a + b;  
      }  
   }  
};  
  
int main() {  
   A^ a = gcnew A;  
   int x = a[3][5];   // C2660  
   int x2 = a[3,5];   // OK  
}  
```  
  
## 使用例  
 テンプレート クラスに定義した新しい演算子が、囲い型以外の型を持つオブジェクトを作成すると、C2660 が発生します。  
  
```  
// C2660e.cpp  
// compile with: /c  
#include <malloc.h>  
  
template <class T> class CA {  
private:  
    static T** line;  
   void* operator new (size_t, int i) {   
      return 0;  
   }  
   void operator delete(void* pMem, int i) {  
      free(pMem);  
   }  
  
public:  
   CA () { new (1) T(); }   // C2660  
   // try the following line instead  
   // CA () { new (1) CA<int>(); }  
};  
  
typedef CA <int> int_CA;  
  
void AAA() {  
   int_CA  list;  
}  
```