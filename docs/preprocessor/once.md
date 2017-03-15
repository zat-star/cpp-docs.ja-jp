---
title: "once | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.once"
  - "once_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "once プラグマ"
  - "プラグマ, once"
ms.assetid: c7517556-6403-4b16-8898-f2aa0a6f685f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# once
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ソース コード ファイルをコンパイルする際、コンパイラによってファイルが 1 回だけ取り込まれる \(開かれる\) ようにします。  
  
## 構文  
  
```  
  
#pragma once  
  
```  
  
## 解説  
 `#pragma once` を使用すると、翻訳単位でファイルの最初の \#include の実行後にコンパイラで同じファイルを開いて読み込むことがないので、ビルド時間を短縮できます。  これを*複数インクルードの最適化*といい、  プリプロセッサのマクロ定義を使用してファイルの内容が複数回インクルードされないようにする、*\#include guard* 表現形式と同様の効果があります。  またこれは、*単一定義規則*の違反を防止するのにも役立ちます。単一定義規則とは、コード内のすべてのテンプレート、型、関数、オブジェクトに 2 つ以上の定義が含まれてはならないという要件です。  
  
 例:  
  
```  
// header.h  
#pragma once  
// Code placed here is included only once per translation unit  
  
```  
  
 新しいコードには `#pragma once` ディレクティブを使用することをお勧めします。これを使えば、プリプロセッサ シンボルによるグローバル名前空間のポリューションが発生しないためです。  またこのディレクティブは、必要な入力量や無駄も少なく、シンボルの競合の原因にもなりません。シンボルの競合とは、異なるヘッダー ファイルで同じプリプロセッサ シンボルがガード値として使用されたときに発生するエラーです。  これは C\+\+ の標準の一部ではありませんが、いくつかの一般的なコンパイラにより移植可能な方法で実装されます。  
  
 同じファイルで \#include guard 表現形式と `#pragma once` の両方を使用する利点はありません。  コメントではないコードまたはプリプロセッサ ディレクティブが標準的な表現形式の前後にくる場合、`#pragma once` ディレティブと同様の方法で、コンパイラにより \#include guard 表現形式が認識され、複数インクルードの最適化が実装されます。  
  
```  
// header.h  
// Demonstration of the #include guard idiom.  
// Note that the defined symbol can be arbitrary.  
#ifndef HEADER_H_     // equivalently, #if !defined HEADER_H_  
#define HEADER_H_  
// Code placed here is included only once per translation unit  
#endif // HEADER_H_  
  
```  
  
 既存のコードとの一貫性を維持するために、`#pragma once` ディレクティブを実装していないコンパイラにコードを移植できるようにする必要がある場合や、複数のインクルードの最適化が不可能である場合は、\#include guard 表現形式をお勧めします。  これは、ファイル システムの別名または別名が設定されたインクルード パスにより、コンパイラが正規のパスを基準に同じインクルード ファイルを識別できなくなるような複雑なプロジェクトで発生する場合があります。  
  
 プリプロセッサ シンボルを使用してその効果を制御する、複数回のインクルードが発生するように設計されているヘッダー ファイルに、`#pragma once` または \#include guard の表現形式を使用しないようにします。  この設計の例については、\<assert.h\> ヘッダー ファイルを参照してください。  また、インクルード ファイルに複数のパスを作成すると、\#include guard と `#pragma once` の両方で複数インクルードの最適化が損なわれるため、インクルード パスを慎重に管理し、それを回避してください。  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)