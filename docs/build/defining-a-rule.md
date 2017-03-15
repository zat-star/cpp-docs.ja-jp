---
title: "規則の定義 | Microsoft Docs"
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
  - "定義 (推論規則を)"
  - "NMAKE プログラム, 推論規則"
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 規則の定義
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*fromext* は依存ファイルの拡張子を表し、*toext* はターゲット ファイルの拡張子を表します。  
  
```  
.fromext.toext:  
   commands  
```  
  
## 解説  
 拡張子では、大文字と小文字が区別されません。  *fromext* および *toext* を表すために、マクロを呼び出すことができます。マクロは、プリプロセス時に展開されます。  *fromext* の前のピリオド \(.\) は、行の先頭に配置する必要があります。  コロン \(:\) の前には、0 個以上の空白またはタブを配置します。  コロンの後に続けられるのは、空白またはタブ、コマンドを指定するためのセミコロン \(;\)、コメントを指定するためのシャープ記号 \(\#\)、あるいは改行文字だけです。  ほかの空白を入れることはできません。  コマンドは、記述ブロックでの場合と同じように指定します。  
  
## さらに詳しくは次のトピックをクリックしてください  
 [規則の検索パス](../build/search-paths-in-rules.md)  
  
## 参照  
 [推論規則](../build/inference-rules.md)