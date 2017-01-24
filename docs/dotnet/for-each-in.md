---
title: "for each、in | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::foreach"
  - "for"
  - "each"
  - "in"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "for each キーワード [C++]"
ms.assetid: 0c3a364b-2747-43f3-bb8d-b7d3b7023f79
caps.latest.revision: 24
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# for each、in
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

配列またはコレクションを反復処理します。  この非標準のキーワードは、C\+\+\/CLI プロジェクトと C\+\+ ネイティブ プロジェクトの両方で使用できます。  ただし、これを使用することはお勧めしません。  代わりに標準の [範囲ベースの for ステートメント \(C\+\+\)](../Topic/Range-based%20for%20Statement%20\(C++\).md) を使用することを検討してください。  
  
## すべてのランタイム  
 **構文**  
  
```  
  
        for each (type identifier in expression) {  
   statements  
}  
  
```  
  
 **パラメーター**  
  
 `type`  
 `identifier` の型。  
  
 `identifier`  
 コレクション要素を表す繰り返し変数。`identifier` が [Tracking Reference Operator](../windows/tracking-reference-operator-cpp-component-extensions.md) の場合は、要素を変更できます。  
  
 `expression`  
 配列式またはコレクション。  コレクション要素は、コンパイラが `identifier` 型に変換できるようにする必要があります。  
  
 `statements`  
 実行する 1 つ以上のステートメントを指定します。  
  
 **解説**  
  
 コレクションを反復処理するために、`for each` ステートメントを使用します。  コレクション内の要素を変更することはできますが、要素を追加または削除することはできません。  
  
 配列内またはコレクション内の要素ごとに、*statements* が実行されます。  コレクション内の全要素に対する繰り返しが完了すると、制御は、`for each` ブロックに続くステートメントに移動します。  
  
 `for each` および `in` は [状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)です。  
  
 詳細情報  
  
-   [for each を使用した STL コレクションの反復処理](../dotnet/iterating-over-stl-collection-by-using-for-each.md)  
  
-   [方法: for each を使用して配列を反復処理する](../dotnet/how-to-iterate-over-arrays-with-for-each.md)  
  
-   [方法: for each を使用してジェネリック コレクションを反復処理する](../dotnet/how-to-iterate-over-a-generic-collection-with-for-each.md)  
  
-   [方法: for each を使用してユーサー定義のコレクションを反復処理する](../Topic/How%20to:%20Iterate%20Over%20a%20User-Defined%20Collection%20with%20for%20each.md)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### 要件  
 コンパイラ オプション: **\/ZW**  
  
### 例  
 この例では、`for each` を使用して文字列を反復処理する方法を示します。  
  
```  
// for_each_string1.cpp  
// compile with: /ZW  
#include <stdio.h>  
using namespace Platform;  
  
ref struct MyClass {  
   property String^ MyStringProperty;  
};  
  
int main() {  
   String^ MyString = ref new String("abcd");  
  
   for each ( char c in MyString )  
      wprintf("%c", c);  
  
   wprintf("/n");  
  
   MyClass^ x = ref new MyClass();  
   x->MyStringProperty = "Testing";  
  
   for each( char c in x->MyStringProperty )  
      wprintf("%c", c);  
}  
```  
  
 **出力**  
  
  **abcd**  
 **テスト**   
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **解説**  
  
 CLR の構文は次の点を除き、**すべてのランタイム** 構文と同じです。  
  
 *expression*  
 マネージ配列式またはコレクション。  コレクション要素は、コンパイラが <xref:System.Object> から *identifier* 型に変換できるようにする必要があります。  
  
 *expression* は、<xref:System.Collections.IEnumerable> を実装する型、<xref:System.Collections.Generic.IEnumerable%601> を実装する型、または `GetEnumerator` メソッドを定義する型と評価されます。このメソッドは、<xref:System.Collections.IEnumerator> を実装する型を返すか、`IEnumerator` の中で定義されているすべてのメソッドを宣言します。  
  
### 要件  
 コンパイラ オプション: **\/clr**  
  
### 例  
 この例では、`for each` を使用して文字列を反復処理する方法を示します。  
  
```  
// for_each_string2.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct MyClass {  
   property String ^ MyStringProperty;  
};  
  
int main() {  
   String ^ MyString = gcnew String("abcd");  
  
   for each ( Char c in MyString )  
      Console::Write(c);  
  
   Console::WriteLine();  
  
   MyClass ^ x = gcnew MyClass();  
   x->MyStringProperty = "Testing";  
  
   for each( Char c in x->MyStringProperty )  
      Console::Write(c);  
}  
```  
  
 **出力**  
  
  **abcd**  
 **テスト**   
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)