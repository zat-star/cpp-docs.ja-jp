---
title: "delegate (C++ コンポーネント拡張) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "delegate_cpp"
  - "delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "delegate キーワード [C++]"
ms.assetid: 03caf23d-7873-4a23-9b34-becf42aaf429
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# delegate (C++ コンポーネント拡張)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

関数ポインターを表す型を宣言します。  
  
## すべてのランタイム  
 デリゲートは、[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]と共通言語ランタイムの両方でサポートされます。  
  
### 解説  
 `delegate` は状況依存のキーワードです。  詳細については、「[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)」を参照してください。  
  
 型がデリゲートかどうかをコンパイル時に検出するには、`__is_delegate()` 型の特徴を使用します。  詳細については、「[Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)」を参照してください。  
  
## Windows ランタイム  
 C\+\+\/CX は、次の構文のデリゲートをサポートします。  
  
### 構文  
  
```cpp  
  
access delegate return-type delegate-type-identifier ([ parameters ])  
```  
  
### パラメーター  
 *access*  
 \(省略可能\) デリゲートのアクセシビリティ。`public` \(既定値\) または `private` を使用できます。  関数のプロトタイプは、`const` または `volatile` のキーワードで修飾することができます。  
  
 *return\-type*  
 関数のプロトタイプの戻り値の型。  
  
 *delegate\-type\-identifier*  
 宣言されたデリゲート型の名前。  
  
 *parameters*  
 \(省略可能\) 関数プロトタイプの型と識別子。  
  
### 解説  
 デリゲートと同じプロトタイプでイベントを宣言するには、*delegate\-type\-identifier* を使用します。  詳細については、「[Delegates \(C\+\+\/CX\) \(デリゲート \(C\+\+\/CX\)\)](../Topic/Delegates%20\(C++-CX\).md)」を参照してください。  
  
### 要件  
 コンパイラ オプション: **\/ZW**  
  
## 共通言語ランタイム  
 共通言語ランタイムは、次の構文のデリゲートをサポートします。  
  
### 構文  
  
```cpp  
  
access delegate function_declaration  
```  
  
### パラメーター  
 *access*  
 \(省略可能\) アセンブリの外部のデリゲートのアクセシビリティとして、public または private を使用できます。既定は private です。クラス内で、デリゲートは任意のアクセシビリティを持つことができます。  
  
 *function\_declaration*  
 デリゲートにバインドできる関数のシグネチャ。  デリゲートの戻り値の型は、任意のマネージ型です。  相互運用性の理由により、デリゲートの戻り値の型を CLS 型とすることをお勧めします。  
  
 非バインドのデリゲートを定義するには、*function\_declaration* の最初のパラメーターでは、オブジェクトの `this` のポインターの型。  詳細については、「[バインドされていないデリゲート](../Topic/Unbound%20Delegates.md)」を参照してください。  
  
### 解説  
 デリゲートはマルチキャストです。"関数ポインター" は、マネージ クラス内の 1 つ以上のメソッドに関連付けることができます。  **delegate** キーワードは、特定のメソッド シグネチャを持つマルチキャスト デリゲート型を定義します。  
  
 また、デリゲートは、静的メソッドなどの値クラスのメソッドにもバインドできます。  
  
 デリゲートには次の特徴があります。  
  
-   **System::MulticastDelegate** から継承します。  
  
-   コンストラクターは、マネージ クラスまたは **NULL** へのポインター \(静的メソッドへのバインドの場合\) と指定した型の完全修飾メソッドの 2 つの引数を受け取ります。  
  
-   `Invoke` というメソッドを持ち、そのシグネチャはデリゲートの宣言されたシグネチャと一致します。  
  
 デリゲートが呼び出されると、関数がアタッチされた順に呼び出されます。  
  
 デリゲートの戻り値は、最後にアタッチされたメンバー関数の戻り値です。  
  
 デリゲートはオーバーロードできません。  
  
 デリゲートには、バインドされたデリゲートとバインドされていないデリゲートがあります。  
  
 バインドされたデリゲートをインスタンス化する場合、最初の引数はオブジェクトの参照である必要があります。デリゲートのインスタンス化の 2 番目の引数は、マネージ クラス オブジェクトのメソッドのアドレスか、または値型のメソッドへのポインターである必要があります。デリゲートのインスタンス化の 2 番目の引数では、完全なクラス スコープ構文のメソッドを指定し、address\-of 演算子を適用する必要があります。  
  
 バインドされていないデリゲートをインスタンス化する場合、最初の引数は、マネージ クラス オブジェクトのメソッドのアドレスか、または値型のメソッドへのポインターである必要があります。この引数では、完全なクラス スコープ構文のメソッドを指定し、address\-of 演算子を適用する必要があります。  
  
 静的またはグローバル関数へのデリゲートを作成する場合に必要なパラメーターは、関数の 1 つだけです \(必要に応じて、関数のアドレスを指定します\)。  
  
 デリゲートの詳細については、以下のトピックを参照してください。  
  
-   [バインドされていないデリゲート](../Topic/Unbound%20Delegates.md)  
  
-   [方法: デリゲートを定義および使用する](../Topic/How%20to:%20Define%20and%20Use%20Delegates%20\(C++-CLI\).md)  
  
-   [Delegate to a Member of a Value Class \(値クラスのメンバーへのデリゲート\)](../misc/how-to-associate-delegates-to-members-of-a-value-class.md)  
  
-   [Delegate to an Unmanaged Function \(アンマネージ関数へのデリゲート\)](../misc/how-to-associate-delegates-to-unmanaged-functions.md)  
  
-   [Composed Delegates \(構成されたデリゲート\)](../misc/how-to-compose-delegates.md)  
  
-   [方法: 関数ポインターを要求するネイティブ関数にデリゲート^ を渡す](../misc/how-to-pass-a-delegate-hat-to-a-native-function-expecting-a-function-pointer.md)  
  
-   [Generic Delegates \(Visual C\+\+\)](../Topic/Generic%20Delegates%20\(Visual%20C++\).md)  
  
### 要件  
 コンパイラ オプション: **\/clr**  
  
### 例  
 **例**  
  
 デリゲートを宣言、初期化、および呼び出す方法を次の例に示します。  
  
```cpp  
// mcppv2_delegate.cpp  
// compile with: /clr  
using namespace System;  
  
// declare a delegate  
public delegate void MyDel(int i);  
  
ref class A {  
public:  
   void func1(int i) {  
      Console::WriteLine("in func1 {0}", i);  
   }  
  
   void func2(int i) {  
      Console::WriteLine("in func2 {0}", i);  
   }  
  
   static void func3(int i) {  
      Console::WriteLine("in static func3 {0}", i);  
   }  
};  
  
int main () {  
   A ^ a = gcnew A;  
  
   // declare a delegate instance  
   MyDel^ DelInst;  
  
   // test if delegate is initialized  
   if (DelInst)  
      DelInst(7);  
  
   // assigning to delegate  
   DelInst = gcnew MyDel(a, &A::func1);  
  
   // invoke delegate  
   if (DelInst)  
      DelInst(8);  
  
   // add a function  
   DelInst += gcnew MyDel(a, &A::func2);  
  
   DelInst(9);  
  
   // remove a function  
   DelInst -= gcnew MyDel(a, &A::func1);  
  
   // invoke delegate with Invoke  
   DelInst->Invoke(10);  
  
   // make delegate to static function  
   MyDel ^ StaticDelInst = gcnew MyDel(&A::func3);  
   StaticDelInst(11);  
}  
```  
  
 **出力**  
  
  **in func1 8**  
 **in func1 9**  
 **in func2 9**  
 **in func2 10**  
 **in static func3 11**   
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)