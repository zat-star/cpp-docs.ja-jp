---
title: "Explicit Overrides  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "overriding, override [C++]"
ms.assetid: 4ec3eaf5-163b-4df8-8f16-7a2ec04c3d0f
caps.latest.revision: 21
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Explicit Overrides  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、明示的に基本クラスまたはインターフェイスのメンバーをオーバーライドする方法について説明します。  名前付きな \(明示\) オーバーライドは別の名前を持つ派生のメソッドのメソッドをオーバーライドする場合にのみ使用してください。  
  
## すべてのランタイム  
 **構文**  
  
```  
  
        overriding-function-declarator = type::function [,type::function] { overriding-function-definition }  
overriding-function-declarator = function { overriding-function-definition }  
```  
  
 **パラメーター**  
  
 *overriding\-function\-declarator*  
 オーバーライドする関数の戻り値の型、名前、引数リスト。オーバーライドする関数がオーバーライドされる関数と同じ名前を持つ必要がないことに注意してください。  
  
 *type*  
 オーバーライドする関数を含む基本型。  
  
 *function*  
 オーバーライドする一つ以上の関数名のコンマ区切りのリスト。  
  
 *overriding\-function\-definition*  
 オーバーライドする関数を定義する関数本体のステートメント。  
  
 **解説**  
  
 メソッド シグネチャのエイリアスを作成するか、または同じシグネチャをメソッドに異なる実装により使用の明示的なオーバーライドします。  
  
 継承された継承された型および型のメンバーの動作の変更については、[オーバーライド指定子](../windows/override-specifiers-cpp-component-extensions.md)を参照してください。  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### 要件  
 コンパイラ オプション: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **解説**  
  
 **\/clr:oldSyntax**でコンパイルされたネイティブ コードまたはアンマネージ コードで明示的にオーバーライドの詳細については、「[明示的なオーバーライド](../cpp/explicit-overrides-cpp.md)」を参照してください。  
  
### 要件  
 コンパイラ オプション: **\/clr**  
  
### 例  
 **例**  
  
 次のコード例は基本インターフェイスで、明示的なオーバーライドを使用して、メンバーの単純な暗黙のオーバーライドと実装を示します。  
  
```  
// explicit_override_1.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
}  
```  
  
 **出力**  
  
  **X::f override of I1::f** **例**  
  
 次のコード例は明示的なオーバーライド構文を使用して一般的なシグネチャを持つすべてのインターフェイス メンバーを実装する方法を示します。  
  
```  
  
// explicit_override_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
interface struct I2 {  
   virtual void f();  
};  
  
ref struct X : public I1, I2 {  
   virtual void f() = I1::f, I2::f {  
      System::Console::WriteLine("X::f override of I1::f and I2::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   I2 ^ MyI2 = gcnew X;  
   MyI -> f();  
   MyI2 -> f();  
}  
```  
  
 **出力**  
  
  **I1::f と I2::f の X::f のオーバーライド**  
 **I1::f と I2::f の X::f のオーバーライド** **例**  
  
 次のコード例は関数のオーバーライドが実装している関数とは異なる名前がどのようになるかを示しています。  
  
```  
// explicit_override_3.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void g() = I1::f {  
      System::Console::WriteLine("X::g");  
   }  
};  
  
int main() {  
   I1 ^ a = gcnew X;  
   a->f();  
}  
```  
  
 **出力**  
  
  **X::g** **例**  
  
 次のコード例はタイプ セーフなコレクションを実装する明示的なインターフェイスの実装を示します。  
  
```  
// explicit_override_4.cpp  
// compile with: /clr /LD  
using namespace System;  
ref class R : ICloneable {  
   int X;  
  
   virtual Object^ C() sealed = ICloneable::Clone {  
      return this->Clone();  
   }  
  
public:  
   R() : X(0) {}  
   R(int x) : X(x) {}  
  
   virtual R^ Clone() {  
      R^ r = gcnew R;  
      r->X = this->X;  
      return r;  
   }  
};  
```  
  
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)