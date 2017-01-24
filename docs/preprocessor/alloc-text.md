---
title: "alloc_text | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.alloc_text"
  - "alloc_text_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "alloc_text プラグマ"
  - "プラグマ, alloc_text"
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# alloc_text
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定した関数定義が存在するコード セクションに名前を付けます。  このプラグマは、名前付き関数の関数宣言子と関数定義との間で指定する必要があります。  
  
## 構文  
  
```  
  
#pragma alloc_text( "  
textsection  
", function1, ... )  
```  
  
## 解説  
 **alloc\_text** プラグマは、C\+\+ メンバー関数またはオーバーロード関数を処理しません。  C リンケージで宣言された関数、つまり、**extern "C"** リンケージ仕様で宣言された関数にのみ適用されます。  C\+\+ リンケージを持つ関数でこのプラグマを使用しようとすると、コンパイラ エラーが生成されます。  
  
 `__based` を使用した関数アドレス指定はサポートされていないため、セクション番号を指定するには **alloc\_text** プラグマを使用する必要があります。  *textsection* で指定する名前は二重引用符で囲む必要があります。  
  
 **alloc\_text** プラグマは、指定された任意の関数の宣言の後、およびこれらの関数の定義の前に記述する必要があります。  
  
 **alloc\_text** プラグマで参照される関数は、プラグマと同じモジュールで定義する必要があります。  これが実行されず、未定義の関数が別のテキスト セクションに後でコンパイルされると、エラーがキャッチされる場合とキャッチされない場合があります。  プログラムは正常に動作しますが、関数は目的のセクションでは割り当てられません。  
  
 **alloc\_text** のその他の制限は次のとおりです。  
  
-   関数内では使用できません。  
  
-   関数が宣言された後で、関数が定義される前に使用する必要があります。  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)