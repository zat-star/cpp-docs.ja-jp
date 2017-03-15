---
title: "safe_cast (C++ Component Extensions) | Microsoft Docs"
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
  - "safe_cast"
  - "safe_cast_cpp"
  - "stdcli::language::safe_cast"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "safe_cast keyword [C++]"
ms.assetid: 4fa688bf-a8ec-49bc-a4c5-f48134efa4f7
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# safe_cast (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`safe_cast` 操作は、指定された式を指定した型で返します \(成功した場合\)。失敗した場合は、`InvalidCastException` をスローします。  
  
## すべてのランタイム  
 \(この言語機能にはランタイムに適用される特記事項がありません。\)  
  
### 構文  
  
```cpp  
  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### パラメーター  
  
### コメント  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 `safe_cast` を使用して、指定された式の型を変更することができます。  変数またはパラメーターを特定の型に問題なく変換できることがわかっている場合、try\-catch ブロックを使用せずに safe\_cast を使用して、開発中のプログラミング エラーを検出することができます。  詳細については、「[キャスト \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh755802.aspx)」を参照してください。  
  
### 構文  
  
```cpp  
  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### パラメーター  
 *type\-id*  
 変換後の *expression* の型。  参照型または値型へのハンドル、値型、参照型または値型への追跡参照。  
  
 *expression*  
 参照型または値型へのハンドル、値型、参照型または値型への追跡参照として評価される式。  
  
### コメント  
 `safe_cast` は *type\-id* で指定された型に *expression* を変換できない `InvalidCastException` をスローします。  `InvalidCastException` をキャッチするには、[\/EH \(例外処理モデル\)](../build/reference/eh-exception-handling-model.md) コンパイラ オプションを指定し、try\/catch ステートメントを使用します。  
  
### 必要条件  
 コンパイラ オプション: **\/ZW**  
  
### 使用例  
 **例**  
  
 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]で `safe_cast` を使用する方法を次のコード例に示します。  
  
```cpp#  
// safe_cast_ZW.cpp  
// compile with: /ZW /EHsc  
  
using namespace default;  
using namespace Platform;  
  
interface class I1 {};  
interface class I2 {};  
interface class I3 {};  
  
ref class X : public I1, public I2 {};  
  
int main(Array<String^>^ args) {  
   I1^ i1 = ref new X;  
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X  
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead  
   try {  
      I3^ i4 = safe_cast<I3^>(i1);   // Fails because i1 is not derived from I3.  
   }   
   catch(InvalidCastException^ ic) {  
     wprintf(L"Caught expected exception: %s\n", ic->Message);  
   }  
}  
```  
  
 **出力**  
  
  **Caught expected exception: InvalidCastException**   
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 `safe_cast` を使用して、式の型を変更し、検証可能な MSIL コードを生成できます。  
  
### 構文  
  
```cpp  
  
[cli]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### パラメーター  
 *type\-id*  
 参照型または値型へのハンドル、値型、参照型または値型への追跡参照。  
  
 *expression*  
 参照型または値型へのハンドル、値型、参照型または値型への追跡参照として評価される式。  
  
### コメント  
 式 `safe_cast<`*type\-id*`>(`*expression*`)` は type\-id 型のオブジェクトにオペランド式を変換します。  
  
 `safe_cast` を使用できるほとんどの場所で、[static\_cast](../cpp/static-cast-operator.md) を使用できます。  ただし、`safe_cast` では確実に検証可能な MSIL が生成されますが、`static_cast` では検証不可能な MSIL が生成される場合があります。  検証可能なコードの詳細については、「[純粋なコードと検証可能なコード](../dotnet/pure-and-verifiable-code-cpp-cli.md)」および「[Peverify.exe \(PEVerify ツール\)](../Topic/Peverify.exe%20\(PEVerify%20Tool\).md)」を参照してください。  
  
 `static_cast` と同様に、`safe_cast` はユーザー定義の変換を呼び出します。  
  
 キャストの詳細については、「[キャスト演算子](../cpp/casting-operators.md)」を参照してください。  
  
 `safe_cast` は **const\_cast**  \(**const** のキャスト\) を適用しません。  
  
 `safe_cast` は cli 名前空間に存在します。  詳細については、「[Platform, default, and cli Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)」を参照してください。  
  
 **safe\_cast** の詳細については、以下を参照してください。  
  
-   [C\-Style Casts with \/clr \(C\+\+\/CLI\)](../windows/c-style-casts-with-clr-cpp-cli.md)  
  
-   [方法: C\+\+\/CLI で safe\_cast を使用する](../Topic/How%20to:%20Use%20safe_cast%20in%20C++-CLI.md)  
  
-   [方法: safe\_cast を使用してダウンキャストする](../misc/how-to-downcast-with-safe-cast.md)  
  
-   [方法: safe\_cast 型およびジェネリック型を使用する](../misc/how-to-use-safe-cast-and-generic-types.md)  
  
-   [方法: safe\_cast およびユーザー定義の変換を使用する](../misc/how-to-use-safe-cast-and-user-defined-conversions.md)  
  
-   [方法: safe\_cast およびボックス化を使用する](../Topic/How%20to:%20Use%20safe_cast%20and%20Boxing.md)  
  
-   [方法: safe\_cast およびボックス化の解除を使用する](../misc/how-to-use-safe-cast-and-unboxing.md)  
  
### 必要条件  
 コンパイラ オプション: **\/clr**  
  
### 使用例  
 **例**  
  
 コンパイラで `static_cast` を使用できないが `safe_cast` を使用できる状況の例の 1 つは、関連していないインターフェイス型の間でのキャストです。  `safe_cast` を使用した場合、コンパイラは変換エラーを生成せず、キャストが可能であるかどうかを実行時に検証します。  
  
```cpp  
// safe_cast.cpp  
// compile with: /clr  
using namespace System;  
  
interface class I1 {};  
interface class I2 {};  
interface class I3 {};  
  
ref class X : public I1, public I2 {};  
  
int main() {  
   I1^ i1 = gcnew X;  
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X  
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead  
   try {  
      I3^ i4 = safe_cast<I3^>(i1);   // fail at runtime, no common type  
   }   
   catch(InvalidCastException^) {  
      Console::WriteLine("Caught expected exception");  
   }  
}  
```  
  
 **出力**  
  
  **Caught expected exception**   
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)