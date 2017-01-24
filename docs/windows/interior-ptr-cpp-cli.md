---
title: "interior_ptr (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "stdcli::language::interior_ptr"
  - "interior_ptr_cpp"
  - "interior_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interior_ptr keyword [C++]"
ms.assetid: 25160f74-569e-492d-9e3c-67ece7486baa
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# interior_ptr (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*内部ポインターは*、オブジェクト自体に参照型の中には、ポインターを宣言します。  内部ポインターは参照のハンドル、値型、ボックス化された型のハンドル、マネージ クラスのメンバー、またはマネージ配列の要素を指すことができます。  
  
## すべてのランタイム  
 \(この言語機能にはランタイムに適用される特記事項がありません。\)  
  
## Windows ランタイム  
 \(この言語機能には Windows ランタイムのみに適用される特記事項がありません。\)  
  
### 要件  
 コンパイラ オプション: **\/ZW**  
  
## 共通言語ランタイム  
 次の例は、内部ポインター構文を示します。  
  
### 構文  
  
```cpp  
cli::interior_ptr<cv_qualifier type> var = &initializer;  
```  
  
### パラメーター  
 *cv\_qualifier*  
 **const** または `volatile` 修飾子。  
  
 *type*  
 *initializer* の型。  
  
 *var*  
 `interior_ptr` 変数の名前。  
  
 *initializer*  
 マネージ配列の参照型、要素、または他のメンバー、ネイティブ ポインターに割り当てることのできるオブジェクト。  
  
### 解説  
 ネイティブ ポインターには、場所がオブジェクトのガベージ コレクターの移動インスタンスになるマネージ ヒープで変更されると、項目を追跡できます。  正しくインスタンスを参照するポインターのランタイムは、最近使用されたオブジェクトへのポインターを更新する必要があります。  
  
 `interior_ptr` はネイティブ ポインター機構のスーパーセットを表します。したがって、ネイティブ ポインターに割り当てることができるものも `interior_ptr`に割り当てることができます。内部ポインターを比較およびポインター演算を含むネイティブ ポインターと操作のセットを実行することができます。  
  
 内部ポインターがスタックでしか宣言できません。内部ポインターがクラスのメンバーとして宣言することはできません。  
  
 内部ポインターがスタックにしかないため、内部ポインターの yield のアドレスにアンマネージ ポインターを受け取ります。  
  
 `interior_ptr`、条件付きステートメントを使用できるようにする `bool`への暗黙の型変換があります。  
  
 ガベージ コレクション ヒープに移動できないオブジェクトを指す内部ポインターを宣言する方法の詳細については [pin\_ptr](../Topic/pin_ptr%20\(C++-CLI\).md)を参照してください。  
  
 `interior_ptr` は cli 名前空間に存在します。詳細については、「[Platform, default, and cli Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)」を参照してください。  
  
 内部ポインターの詳細については、参照します  
  
-   [How to: Declare and Use Interior Pointers and Managed Arrays \(C\+\+\/CLI\)](../windows/how-to-declare-and-use-interior-pointers-and-managed-arrays-cpp-cli.md)  
  
-   [How to: Declare Value Types with the interior\_ptr Keyword \(C\+\+\/CLI\)](../windows/how-to-declare-value-types-with-the-interior-ptr-keyword-cpp-cli.md)  
  
-   [How to: Overload Functions with Interior Pointers and Native Pointers \(C\+\+\/CLI\)](../windows/how-to-overload-functions-with-interior-pointers-and-native-pointers-cpp-cli.md)  
  
-   [How to: Declare Interior Pointers with the const Keyword \(C\+\+\/CLI\)](../windows/how-to-declare-interior-pointers-with-the-const-keyword-cpp-cli.md)  
  
### 要件  
 コンパイラ オプション: **\/clr**  
  
### 例  
 **例**  
  
 次の例は、参照型に内部ポインターを宣言および使用する方法を示します。  
  
```cpp  
// interior_ptr.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyClass {  
public:  
   int data;  
};  
  
int main() {  
   MyClass ^ h_MyClass = gcnew MyClass;  
   h_MyClass->data = 1;  
   Console::WriteLine(h_MyClass->data);  
  
   interior_ptr<int> p = &(h_MyClass->data);  
   *p = 2;  
   Console::WriteLine(h_MyClass->data);  
  
   // alternatively  
   interior_ptr<MyClass ^> p2 = &h_MyClass;  
   (*p2)->data = 3;  
   Console::WriteLine((*p2)->data);  
}  
```  
  
 **出力**  
  
 **1**   
**2**   
**3**   
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)