---
title: "コンパイラ エラー C2259 | Microsoft Docs"
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
  - "C2259"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2259"
ms.assetid: e458236f-bdea-4786-9aa6-a98d8bffa5f4
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2259
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'クラス' : 抽象クラスをインスタンス化できません。  
  
 抽象クラスまたは抽象構造体のインスタンスが宣言されています。  
  
 1 つ以上の純粋仮想関数を持つクラスまたは構造体をインスタンス化することはできません。  派生クラスのオブジェクトをインスタンス化するには、派生クラスが各純粋仮想関数をオーバーライドする必要があります。  
  
 詳細については、「[暗黙的な抽象クラス](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Implicitly_abstract_classes)」を参照してください。  
  
 次の例では警告 C2259 が生成されます。  
  
```  
// C2259.cpp  
// compile with: /c  
class V {  
public:  
   void virtual func() = 0;  
};  
class A : public V {};  
class B : public V {  
public:  
   void func();  
};  
V v;  // C2259, V is an abstract class  
A a;  // C2259, A inherits func() as pure virtual  
B b;  // OK, B defines func()  
```  
  
 インターフェイスから派生して、パブリック以外のアクセス許可を持つインターフェイス メソッドを派生クラスに実装する場合は、常に C2259 が発生する可能性があります。これは、コンパイラでは、派生クラスに実装されたインターフェイス メソッドはパブリック アクセスを持つことが想定されているために発生します。  より制限の厳しいアクセス許可を持つインターフェイスのメンバー関数を実装する場合、コンパイラはそれらをインターフェイスに定義されるインターフェイス メソッドの実装とは見なさず、代わりにその派生クラスを抽象クラスとします。  
  
 この問題を回避する方法は 2 つあります。  
  
-   実装されるメソッドのアクセス許可をパブリックにします。  
  
-   派生クラスに実装されるインターフェイス メソッドに対してスコープ解決演算子を使用して、実装されるメソッド名をインターフェイスの名前で修飾します。  
  
 C2259 は、**\/Zc:wchar\_t** が既定でオンになったため、Visual C\+\+ 2005 で行った準拠作業の結果として発生することもあります。  この場合に C2599 エラーを解決するには、**\/Zc:wchar\_t\-** を指定してコンパイルすることによって以前のバージョンの動作を指定します。可能であれば、互換性を維持できるように型を更新します。  詳細については、「[\/Zc:wchar\_t \(wchar\_t をネイティブ型として認識\)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md)」を参照してください。  
  
 次の例では警告 C2259 が生成されます。  
  
```  
// C2259b.cpp  
// compile with: /c  
#include <windows.h>   
  
class MyClass {  
public:  
   // WCHAR now typedef'ed to wchar_t  
   virtual void func(WCHAR*) = 0;  
};  
  
class MyClass2 : MyClass {  
public:  
   void func(unsigned short*);  
};  
  
MyClass2 x;   // C2259  
  
// OK  
class MyClass3 {  
public:  
   virtual void func(WCHAR*) = 0;  
   virtual void func2(wchar_t*) = 0;  
   virtual void func3(unsigned short*) = 0;  
};  
  
class MyClass4 : MyClass3 {  
public:  
   void func(WCHAR*) {}  
   void func2(wchar_t*) {}  
   void func3(unsigned short*) {}  
};  
  
MyClass4 y;  
```  
  
 次の例では警告 C2259 が生成されます。  
  
```  
// C2259c.cpp  
// compile with: /clr  
interface class MyInterface {  
   void MyMethod();  
};  
  
ref class MyDerivedClass: public MyInterface {  
private:  
   // Uncomment the following line to resolve.  
   // public:  
   void MyMethod(){}  
   // or the following line  
   // void MyInterface::MyMethod() {};  
};  
  
int main() {  
   MyDerivedClass^ instance = gcnew MyDerivedClass; // C2259  
}  
```  
  
 次の例では警告 C2259 が生成されます。  
  
```  
// C2259d.cpp  
// compile with: /clr:oldSyntax  
public __gc __interface MyInterface {  
   void MyMethod();  
};  
  
__gc class MyDerivedClass : public MyInterface {  
// Uncomment the following line to resolve.  
// public:  
   void MyMethod() {};  
   // or the following line  
   // void MyInterface::MyMethod() {};  
};  
  
int main() {  
   MyDerivedClass *instance = new MyDerivedClass();   // C2259  
}  
```