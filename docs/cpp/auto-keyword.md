---
title: "auto キーワード | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "auto"
  - "auto_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto キーワード"
  - "自動ストレージ クラス, auto キーワード"
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# auto キーワード
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`auto` キーワードは宣言指定子です。  ただし、C\+\+ 標準ではこのキーワードの元の意味と変更後の意味が定義されます。  [!INCLUDE[cpp_dev10_long](../Token/cpp_dev10_long_md.md)] より前のバージョンでは、`auto` キーワードは、*ローカルな寿命*クラスの変数、つまりローカルの有効期間を持つ変数を宣言します。  [!INCLUDE[cpp_dev10_long](../Token/cpp_dev10_long_md.md)] 以降、`auto` キーワードは、その宣言の初期化式から変数の型を推測し、変数を宣言します。  [\/Zc:auto&#91;\-&#93;](../build/reference/zc-auto-deduce-variable-type.md) コンパイラ オプションは、`auto` のキーワードの意味を制御します。  
  
## 構文  
  
```cpp  
auto declarator ;  
auto declarator initializer;  
```  
  
## 解説  
 `auto` キーワードの定義は、C\+\+ プログラミング言語では変化しますが、C プログラミング言語では変化しません。  
  
 ここからのトピックでは、`auto` キーワードと、対応するコンパイラ オプションについて説明します。  
  
-   「[auto](../cpp/auto-cpp.md)」では、`auto` キーワードの新しい定義を説明します。  
  
-   「[\(NOTINBUILD\)auto Keyword \(Storage\-Class Specifier\)](http://msdn.microsoft.com/ja-jp/c7d0cecf-393d-4058-a6e6-b39e31d9edb0)」では、`auto` キーワードの元の定義を説明します。  
  
-   [\/Zc:auto \(変数の型の推測\)](../build/reference/zc-auto-deduce-variable-type.md) は、コンパイラに対し、変数の宣言に `auto` キーワードのどの定義を使用するかを指定するコンパイラ オプションを説明します。  
  
## 参照  
 [\(NOTINBUILD\)Storage\-Class Specifiers](http://msdn.microsoft.com/ja-jp/10b3d22d-cb40-450b-994b-08cf9a211b6c)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)