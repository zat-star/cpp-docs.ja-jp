---
title: "DUMPBIN コマンド ライン | Microsoft Docs"
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
  - "dumpbin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DUMPBIN プログラム, コマンド ライン"
ms.assetid: e6ad17d3-965d-41aa-9dfd-75bb073718d4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# DUMPBIN コマンド ライン
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

DUMPBIN を実行するには、次の構文を使用します。  
  
```  
DUMPBIN [options] files...  
```  
  
 1 つ以上のバイナリ ファイルと、出力情報を指定するオプションを入力します。  情報は標準出力に表示されます。  この情報は、ファイルにリダイレクトすることも、\/OUT オプションで名前を指定したファイルに出力することもできます。  
  
 オプションを指定せずにファイル名だけを指定して DUMPBIN を実行すると、\/SUMMARY を指定したときと同じ内容が出力されます。  
  
 「`dumpbin`」とだけ入力してほかに何も指定しないと、オプションの使い方についての簡単な説明が表示されます。  
  
## 参照  
 [C と C\+\+ のビルド ツール](../Topic/C-C++%20Build%20Tools.md)   
 [DUMPBIN リファレンス](../../build/reference/dumpbin-reference.md)