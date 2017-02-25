---
title: "プリプロセッサ ディレクティブ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ディレクティブ, プリプロセッサ"
  - "プリプロセッサ, ディレクティブ"
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# プリプロセッサ ディレクティブ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`#define` や **\#ifdef** のようなプリプロセッサ ディレクティブは通常、異なる実行環境でソース プログラムを簡単に変更したりコンパイルしたりするために使用されます。  ソース ファイルのディレクティブはプリプロセッサに特定のアクションを実行するよう通知します。  たとえば、プリプロセッサは、テキストのトークンを置き換えたり、ソース ファイルに他のファイルの内容を挿入したり、テキストのセクションの削除によりファイルの一部のコンパイルを中止したりできます。  プリプロセッサ行は、マクロの展開の前に認識され、実行されます。  したがって、マクロがプリプロセッサ コマンドのように見えるコマンドに展開されても、そのコマンドはプリプロセッサによって認識されません。  
  
 プリプロセッサ ステートメントは、ソース ファイル ステートメントと同じ文字セットを使用しますが、エスケープ シーケンスはサポートされていません。  プリプロセッサ ステートメントで使用される文字セットは、[実行文字セット](http://msdn.microsoft.com/ja-jp/a7901c61-524d-47c6-beb6-d9dacc2e72ed)と同じです。  プリプロセッサは、負の文字値も認識します。  
  
 プリプロセッサは次のディレクティブを認識します。  
  
|||||  
|-|-|-|-|  
|[\#define](../preprocessor/hash-define-directive-c-cpp.md)|[\#error](../preprocessor/hash-error-directive-c-cpp.md)|[\#import](../Topic/%23import%20Directive%20\(C++\).md)|[\#undef](../preprocessor/hash-undef-directive-c-cpp.md)|  
|[\#elif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[\#if](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[\#include](../preprocessor/hash-include-directive-c-cpp.md)|[\#using](../preprocessor/hash-using-directive-cpp.md)|  
|[\#else](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[\#ifdef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[\#line](../Topic/%23line%20Directive%20\(C-C++\).md)|[\#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|  
|[\#ifndef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[\#pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)|||  
  
 シャープ記号 \(**\#**\) は、ディレクティブを含む行の最初の空白以外の文字である必要があります。空白文字は、ディレクティブのシャープ記号と最初の文字の間に挿入できます。  一部のディレクティブには、引数または値が含まれます。  ディレクティブに続くテキスト \(ディレクティブの一部である引数または値を除く\) は、前に単一行のコメント デリミター \(**\/\/**\) を付けるか、またはコメント デリミター \(**\/\* \*\/**\) で囲む必要があります。  プリプロセッサ ディレクティブを含む行は、円記号 \(**\\**\) を行末マーカーの直前に置くことにより続行できます。  
  
 プリプロセッサ ディレクティブはソース ファイル内の任意の場所で使用できますが、ソース ファイルの残りの部分だけに適用されます。  
  
## 参照  
 [プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)   
 [定義済みマクロ](../preprocessor/predefined-macros.md)   
 [C\/C\+\+ プリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)