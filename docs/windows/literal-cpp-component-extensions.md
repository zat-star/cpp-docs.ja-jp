---
title: "literal (C++ Component Extensions) | Microsoft Docs"
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
  - "literal"
  - "literal_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "literal keyword [C++]"
ms.assetid: 6b1a1f36-2e1d-4a23-8eb6-172f4f3c477f
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# literal (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\/clr** コンパイルの `literal` が `static const` 変数のネイティブ等価なので変数 \(データ メンバー\) を説明しました。  
  
## すべてのプラットフォーム  
 **解説**  
  
 \(この言語機能にはランタイムに適用される特記事項がありません。\)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **解説**  
  
 \(この言語機能には Windows ランタイムのみに適用される特記事項がありません。\)  
  
### 要件  
 コンパイラ オプション: **\/ZW**  
  
## 共通言語ランタイム  
  
## 解説  
 `literal` とマークされたデータ メンバーは、宣言時に値が定数整数、列挙型、または文字列型である初期化されなければ。  初期化子式の型から静的な定数のデータ メンバーの型への変換はユーザー定義変換を必要とすることはできません。  
  
 メモリは、ランタイム リテラル フィールドには; コンパイラは、クラスのメタデータのみに値を挿入します。  
  
 変数に指定された `static const` は他のコンパイラとメタデータでは使用できません。  
  
 詳細については、「[スタティック](../misc/static-cpp.md)」および「[const](../cpp/const-cpp.md)」を参照してください。  
  
 `literal` は状況依存のキーワードです。  詳細については、「[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 この例では `literal` の変数が `static`を意味することを示しています。  
  
```  
// mcppv2_literal.cpp  
// compile with: /clr  
ref struct X {  
   literal int i = 4;  
};  
  
int main() {  
   int value = X::i;  
}  
```  
  
## 使用例  
 次の例は、メタデータでリテラルの影響を示す:  
  
```  
// mcppv2_literal2.cpp  
// compile with: /clr /LD  
public ref struct A {  
   literal int lit = 0;  
   static const int sc = 1;  
};  
```  
  
 `sc` と `lit`のメタデータの相違を確認する: `modopt` のディレクティブが意味する `sc`に適用される他のコンパイラで無視できることを示します。  
  
```  
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x0000000A)  
```  
  
```  
.field public static literal int32 lit = int32(0x0000000A)  
```  
  
## 使用例  
 C\# で記述された次の例では、前の例で作成したメタデータを参照し、`literal` と `static const` 変数の影響を示す:  
  
```  
// mcppv2_literal3.cs  
// compile with: /reference:mcppv2_literal2.dll  
// A C# program  
class B {  
   public static void Main() {  
      // OK  
      System.Console.WriteLine(A.lit);  
      System.Console.WriteLine(A.sc);  
  
      // C# does not enforce C++ const  
      A.sc = 9;  
      System.Console.WriteLine(A.sc);  
  
      // C# enforces const for a literal  
      A.lit = 9;   // CS0131  
  
      // you can assign a C++ literal variable to a C# const variable  
      const int i = A.lit;  
      System.Console.WriteLine(i);  
  
      // but you cannot assign a C++ static const variable  
      // to a C# const variable  
      const int j = A.sc;   // CS0133  
      System.Console.WriteLine(j);  
   }  
}  
```  
  
## 要件  
 コンパイラ オプション: **\/clr**  
  
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)