---
title: "致命的なエラー C1001 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1001"
ms.assetid: 5736cdb3-22c8-4fad-aa85-d5e0d2b232f4
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# 致命的なエラー C1001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

内部コンパイラ エラー  \(コンパイラ ファイル file, 行 number\)  
  
 コンパイラは、構成体に対して適切なコードを生成できません。式と最適化オプションの組み合わせが原因と考えられます。  1 つ以上の最適化オプションを解除してから、エラー メッセージで示された行を含む関数を再コンパイルしてください。  
  
 1 つ以上の最適化オプションを削除すると、問題を修正できる場合があります。  エラーの原因となっていたオプションを判別するには、一度に 1 つずつオプションを解除して、エラー メッセージが出力されなくなるまで再コンパイルを繰り返します。  よく問題となるオプションは、**\/Og**、**\/Oi**、および `/Oa` です。  一度問題となるオプションを特定できれば、[optimize](../../preprocessor/optimize.md) プラグマを使用してエラーが発生した関数についてそのオプションを無効にし、その他のモジュールでは引き続きこのオプションを使用できます。  
  
 Microsoft サポート技術情報の文書に C1001 に関する詳細な情報があります。; 参照してください [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;134650](http://support.microsoft.com/default.aspx?scid=kb;en-us;134650)。  
  
 エラーが報告された行やその前後の数行のコードを書き直してください。