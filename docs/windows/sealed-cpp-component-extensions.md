---
title: "sealed (C++ コンポーネント拡張) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sealed_cpp
- sealed
dev_langs:
- C++
helpviewer_keywords:
- sealed keyword [C++]
ms.assetid: 3d0d688a-41aa-45f5-a25a-65c44206521e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb8a8b7ea695d878235898a8741adf04ba91748c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="sealed--c-component-extensions"></a>sealed (C++ コンポーネント拡張)
`sealed` は ref クラスの状況依存のキーワードであり、仮想メンバーがオーバーライドできないこと、または型を基本型として使用できないことを示します。  
  
> [!NOTE]
>  ISO c 11 標準の言語が、[最終](../cpp/final-specifier.md)キーワードで、Visual Studio ではサポートされています。 標準クラスでは `final` を、ref クラスでは `sealed` を使用してください。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
  
## <a name="syntax"></a>構文
  
```  
ref class identifier sealed {...};  
virtual return-type identifier() sealed {...};  
```  
  
### <a name="parameters"></a>パラメーター  
  
 *identifier*  
 関数またはクラスの名前。  
  
 *戻り値の型*  
 関数によって返される型。  
  
## <a name="remarks"></a>コメント  
  
 最初の構文例ではクラスがシールされます。 2 番目の例では仮想関数がシールされます。  
  
 `sealed`キーワードはネイティブ ターゲットの場合、および Windows ランタイムと共通言語ランタイム (CLR) のも有効です。 詳細については、次を参照してください。[オーバーライド指定子とネイティブ コンパイル](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)です。  
  
 使用して、型がシールされているかどうかは、コンパイル時に検出することができます、`__is_sealed(type)`型の特徴です。 詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)です。  
  
 `sealed` は状況依存のキーワードです。  詳細については、次を参照してください。[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)です。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 参照してください[Ref クラスと構造体](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx)です。  
  
### <a name="requirements"></a>必要条件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム  
 (この言語機能には共通言語ランタイムのみに適用される特記事項がありません。)  
  
### <a name="requirements"></a>必要条件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
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
  
```Output  
X::f override of I1::f  
X::f override of I1::g  
Y::f override of I1::f  
```  
  
 次のコード例では、シール済みというマークをクラスに付ける方法を示します。  
  
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
  
## <a name="see-also"></a>参照  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)