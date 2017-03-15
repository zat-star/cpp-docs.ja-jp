---
title: "参照型の C++ スタック セマンティクス | Microsoft Docs"
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
  - "参照型, C++ スタック セマンティクス"
ms.assetid: 319a1304-f4a4-4079-8b84-01cec847d531
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 参照型の C++ スタック セマンティクス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 2005 以前では、参照型のインスタンスがガベージ コレクションによって収集されたヒープのオブジェクトを作成する `new` の演算子を使用して作成できます。  ただし、スタックのネイティブ型のインスタンスを作成するために、同じ構文を使用して、参照型のインスタンスを作成できます。  このため、参照型のオブジェクトを作成するために [ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) を使用する必要はありません。  およびオブジェクトがスコープ外に出ると、コンパイラがオブジェクトのデストラクターを呼び出します。  
  
## 解説  
 スタック セマンティクスを使用して参照型のインスタンスを作成すると、コンパイラは内部的にガベージ コレクションが行われるヒープのインスタンスを作成します。`gcnew`を使用\)。  
  
 関数のシグネチャまたは戻り値の型が値渡しの参照型のインスタンスが含まれる場合、特別な処理を必要とするものとしてメタデータでマークされます。modreq と\)。  この特別な処理は現在 Visual C\+\+ クライアントでのみ利用できません; 他の言語では現在 Stack Semantics で作成された参照型を使用するデータまたは処理関数をサポートしていません。  
  
 Stack Semantics の代わりに `gcnew` \(動的割り当て\) を使用する 1 とおりの原因は型にデストラクターが必要です。  この関数に Visual C\+\+ 以外の言語で使用する場合は、関数シグネチャで Stack Semantics で作成された参照型を使用して可能である必要があります。  
  
 コンパイラは参照型のコピー コンストラクターを生成しません。  したがって、シグネチャに値渡しの参照型を使用する関数を定義する場合は、参照型のコピー コンストラクターを定義する必要があります。  参照型のコピー コンストラクターは次のフォームのシグネチャを持つ: `R(R%){}`。  
  
 コンパイラは参照型の既定の代入演算子は生成されません。  代入演算子は、オブジェクトをスタック セマンティクスを使用して作成し、スタック セマンティクスを使用して作成された既存のオブジェクトを初期化することができます。  参照型の代入演算子は次のフォームのシグネチャを持つ: `void operator=( R% ){}`。  
  
 型のデストラクターが必要なリソースを"使用 Stack Semantics 解放する場合は、明示的にデストラクターを呼び出す必要はありません \(または `delete`を呼び出すため\)。  参照型のデストラクターの詳細については、「[Visual C\+\+ のデストラクターおよびファイナライザー](../misc/destructors-and-finalizers-in-visual-cpp.md)」を参照してください。  
  
 コンパイラが生成した代入演算子は次の加算と通常の C\+\+ の標準規則に従って:  
  
-   型が参照型のハンドルであるコピーされたすべての非静的データ メンバーが浅いです \(型がポインターである非静的のように扱うデータ メンバー。  
  
-   型が値型のコピーされたすべての非静的データ メンバーが浅いです。  
  
-   型は、参照型のインスタンスであるすべての非静的データ メンバーが参照型のコピー コンストラクターへの呼び出しを呼び出します。  
  
 コンパイラは、基になるハンドル型にスタック セマンティクスを使用して作成された参照型のインスタンスを変換するに `%` の単項演算子が用意されています。  
  
 次の参照型は、Stack Semantics で使用できません:  
  
-   [delegate](../windows/delegate-cpp-component-extensions.md)  
  
-   [Arrays](../windows/arrays-cpp-component-extensions.md)  
  
-   <xref:System.String>  
  
## 例  
  
### 説明  
 次のコード サンプルでは、スタックの意味を持つ参照型のインスタンスをどのように、代入演算子、コピー コンストラクター宣言作業する方法と、スタック セマンティクスを使用して作成された参照型で追跡参照を初期化する方法を示します。  
  
### コード  
  
```  
// stack_semantics_for_reference_types.cpp  
// compile with: /clr  
ref class R {  
public:  
   int i;  
   R(){}  
  
   // assignment operator  
   void operator=(R% r) {  
      i = r.i;  
   }  
  
   // copy constructor  
   R(R% r) : i(r.i) {}  
};  
  
void Test(R r) {}   // requires copy constructor  
  
int main() {  
   R r1;  
   r1.i = 98;  
  
   R r2(r1);   // requires copy constructor  
   System::Console::WriteLine(r1.i);  
   System::Console::WriteLine(r2.i);  
  
   // use % unary operator to convert instance using stack semantics  
   // to its underlying handle  
   R ^ r3 = %r1;  
   System::Console::WriteLine(r3->i);  
  
   Test(r1);  
  
   R r4;  
   R r5;  
   r5.i = 13;  
   r4 = r5;   // requires a user-defined assignment operator  
   System::Console::WriteLine(r4.i);  
  
   // initialize tracking reference  
   R % r6 = r4;  
   System::Console::WriteLine(r6.i);  
}  
```  
  
### 出力  
  
```  
98  
98  
98  
13  
13  
```  
  
## 参照  
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)