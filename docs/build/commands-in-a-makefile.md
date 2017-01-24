---
title: "メイクファイルのコマンド | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コマンド, メイクファイル"
ms.assetid: 8085517e-42f4-493b-b8f8-44311fc08c64
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# メイクファイルのコマンド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

記述ブロックまたは推論規則では、依存関係が古い場合に実行するコマンド ブロックを指定します。  NMAKE は、\/S、**.SILENT**、**\!CMDSWITCHES**、または @ が使用されない限り、各コマンドを実行する前にそのコマンドを表示します。  記述ブロックの後にコマンド ブロックがない場合、NMAKE は適切な推論規則を検索します。  
  
 コマンド ブロックでは、コマンドがそれぞれ独自の行で指定されます。  依存関係または規則とコマンド ブロックの間に空行は挿入できません。  ただし、空白またはタブだけが含まれる行は挿入できます。この行は null コマンドと解釈され、エラーは発生しません。  コマンド ラインの間では、空行を挿入できます。  
  
 コマンド ラインは、空白またはタブで開始します。  改行文字が後続する円記号 \(\\\) は、コマンドでは空白として解釈されます。行末で円記号を使用すると、コマンドを次行に続けることができます。  空白やタブなどのほかの文字が円記号に続く場合、その円記号はリテラルとして解釈されます。  
  
 コマンド ブロックが後続するかどうかに関係なく、セミコロン \(;\) が前に付いたコマンドは、依存関係行または推論規則で指定できます。  
  
```  
project.obj : project.c project.h ; cl /c project.c  
```  
  
## さらに詳しくは次のトピックをクリックしてください  
 [コマンド修飾子](../Topic/Command%20Modifiers.md)  
  
 [ファイル名分割構文](../build/filename-parts-syntax.md)  
  
 [メイクファイルのインライン ファイル](../build/inline-files-in-a-makefile.md)  
  
## 参照  
 [NMAKE リファレンス](../build/nmake-reference.md)