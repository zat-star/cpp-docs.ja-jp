---
title: "リンカー ツールの警告 LNK4006 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4006"
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# リンカー ツールの警告 LNK4006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

symbol は object で定義されています。2 つ目以降の定義は無視されます。  
  
 指定された `symbol` は装飾して表示され、重複定義されています。  この警告が発生した場合、`symbol` は 2 回追加されますが、最初の形式だけが使用されます。  
  
 2 つのインポート ライブラリを 1 つにマージしようとすると、この警告が出力されることがあります。  
  
 C ランタイム ライブラリを再度ビルドする場合は、このメッセージを無視してかまいません。  
  
### 次のような解決策を使用して問題を解決するには  
  
1.  装飾された形式で表示された `symbol` は、コンパイル時に [\/Gy](../../build/reference/gy-enable-function-level-linking.md) オプションを付けて作成された、パッケージ化された関数です。  このシンボルは 2 つ以上のファイルに含まれていますが、ファイルが別個にコンパイルされたときに変更されています。  この `symbol` を含むすべてのファイルを再コンパイルしてください。  
  
2.  指定された `symbol` が、異なるライブラリにある 2 つのメンバーで異なって定義されている可能性があります。  
  
3.  絶対シンボルの定義が 2 回行われ、それぞれの定義で値が異なっています。  
  
4.  ライブラリの結合中にこのメッセージを受け取った場合、追加中のライブラリに `symbol` が既に存在しています。