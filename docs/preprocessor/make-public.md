---
title: "make_public | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.make_public"
  - "make_public_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_public プラグマ"
  - "プラグマ, make_public プラグマ"
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# make_public
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ネイティブ型はパブリック アセンブリのアクセシビリティが必要であることを示します。  
  
## 構文  
  
```  
#pragma make_public(type)  
```  
  
#### パラメーター  
 `type` は、パブリック アセンブリのアクセシビリティを設定する型の名前です。  
  
## 解説  
 `make_public` は、参照するネイティブ型が、変更できない .h ファイルにある場合に便利です。  パブリック関数のシグニチャでパブリック アセンブリ可視性を持つ型としてネイティブ型を使用する場合は、ネイティブ型にパブリック アセンブリ アクセシビリティもある必要があります。そうでない場合、コンパイラは警告を発行します。  
  
 `make_public` はグローバル スコープで指定する必要があり、宣言された時点からソース コード ファイルの末尾まで有効です。  
  
 ネイティブ型は暗黙的または明示的にプライベートにすることができます。詳細については「[型の可視性](../Topic/Type%20Visibility.md)」を参照してください。  
  
## 使用例  
 次のサンプルは、2 つのネイティブ構造体の定義を含む .h ファイルの内容です。  
  
```  
// make_public_pragma.h  
struct Native_Struct_1 { int i; };  
struct Native_Struct_2 { int i; };  
```  
  
## 使用例  
 次のコード例は、ヘッダー ファイルを実行し、`make_public` を使用してネイティブの構造がパブリックとして明示的にマークされない限り、ユーザーがパブリック関数とパブリック マネージ型を使用しようとすると、コンパイラが警告を生成することを示します。  
  
```  
// make_public_pragma.cpp  
// compile with: /c /clr /W1  
#pragma warning (default : 4692)  
#include "make_public_pragma.h"  
#pragma make_public(Native_Struct_1)  
  
public ref struct A {  
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK  
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692  
};  
```  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)