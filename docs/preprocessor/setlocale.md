---
title: "setlocale | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "setlocale_CPP"
  - "vc-pragma.setlocale"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "プラグマ, setlocale"
  - "setlocale プラグマ"
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# setlocale
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ワイド文字定数、リテラル文字列を変換するときに使用するロケール \(国\/地域および言語\) を定義します。  
  
## 構文  
  
```  
  
#pragma setlocale( "[locale-string]" )  
```  
  
## 解説  
 マルチバイト文字をワイド文字に変換するアルゴリズムはロケールやコンパイルによって異なる場合や、実行可能ファイルを実行するロケールとは別のロケールでコンパイルされる場合があるため、このプラグマはコンパイル時にターゲットのロケールを指定する方法を提供します。  これによって、ワイド文字列が必ず正しい形式で保存されるようになります。  
  
 既定の *locale\-string* は "" です。  
  
 "C" ロケールは、文字列の各文字を `wchar_t` \(unsigned short\) として値にマップします。  `setlocale` に有効なその他の値は、[言語文字列](../c-runtime-library/language-strings.md)リスト内にあるエントリです。  たとえば、次のように発行します。  
  
```  
#pragma setlocale("dutch")  
```  
  
 言語文字列を発行する機能は、コンピューター上でのコード ページおよび言語 ID のサポートによって異なります。  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)