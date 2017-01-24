---
title: "sealed  (C++ Component Extensions) | Microsoft Docs"
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
  - "sealed_cpp"
  - "sealed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sealed keyword [C++]"
ms.assetid: 3d0d688a-41aa-45f5-a25a-65c44206521e
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# sealed  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`sealed` は ref クラスの状況依存のキーワードであり、仮想メンバーがオーバーライドできないこと、または型を基本型として使用できないことを示します。  
  
> [!NOTE]
>  ISO C\+\+11 標準の言語には [final](../cpp/final-specifier.md) キーワードがあり、これは Visual Studio でサポートされています。  標準クラスでは `final` を、ref クラスでは `sealed` を使用してください。  
  
## すべてのランタイム  
 **構文**  
  
```  
  
ref class identifier sealed {...};  
virtual return-type identifier() sealed {...};  
  
```  
  
 **パラメーター**  
  
 *identifier*  
 関数またはクラスの名前。  
  
 *return\-type*  
 関数によって返される型。  
  
 **コメント**  
  
 最初の構文例ではクラスがシールされます。  2 番目の例では仮想関数がシールされます。  
  
 `sealed` キーワードはネイティブ ターゲットで有効であり、[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] や共通言語ランタイム \(CLR\) でも有効です。  詳細については、「[オーバーライド指定子とネイティブ コンパイル](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)」を参照してください。  
  
 `__is_sealed (` `type` `)` 型の特徴を使用することにより、型がシールされているかどうかをコンパイル時に判断することができます。  詳細については、「[Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)」を参照してください。  
  
 `sealed` は状況依存のキーワードです。  詳細については、「[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)」を参照してください。  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 「[Ref クラスと構造体](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx)」を参照してください。  
  
### 必要条件  
 コンパイラ オプション: **\/ZW**  
  
## 共通言語ランタイム  
 \(この言語機能には共通言語ランタイムのみに適用される特記事項がありません。\)  
  
### 必要条件  
 コンパイラ オプション: **\/clr**  
  
### 例  
 次のコード例は、仮想メンバーに対する `sealed` の効果を示します。  
  
```cpp  
// sealed_keyword.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
   virtual void g();  
};  
  
ref class X : I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
  
   virtual void g() sealed {  
      System::Console::WriteLine("X::f override of I1::g");  
   }  
};  
  
ref class Y : public X {  
public:  
   virtual void f() override {  
      System::Console::WriteLine("Y::f override of I1::f");  
   }  
  
   /*  
   // the following override generates a compiler error  
   virtual void g() override {  
      System::Console::WriteLine("Y::g override of I1::g");  
   }    
   */  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
   MyI -> g();  
  
   I1 ^ MyI2 = gcnew Y;  
   MyI2 -> f();  
}  
```  
  
 **出力**  
  
  **X::f override of I1::f**  
 **X::f override of I1::g**  
 **Y::f override of I1::f** 次のコード例では、シール済みというマークをクラスに付ける方法を示します。  
  
```cpp  
// sealed_keyword_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X sealed : I1 {  
public:  
   virtual void f() override {}  
};  
  
ref class Y : public X {   // C3246 base class X is sealed  
public:  
   virtual void f() override {}  
};  
```  
  
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)