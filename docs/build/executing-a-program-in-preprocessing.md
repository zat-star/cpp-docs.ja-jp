---
title: "プリプロセスでのプログラムの実行 | Microsoft Docs"
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
  - "プログラムの実行 [C++]"
ms.assetid: 5ecf123a-20e5-40cd-b8d8-dd5a9fdd4b24
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# プリプロセスでのプログラムの実行
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プリプロセス時にコマンドの終了コードを使用するには、任意の引数と一緒にコマンドを指定し、角かっこ \(\[ \]\) で囲みます。  マクロは、コマンドの実行前に展開されます。  コマンドの指定は、コマンドの終了コードで置換されます。コマンドの終了コードは、プリプロセスを制御するために式で使用できます。  
  
## 参照  
 [メイクファイル プリプロセスの式](../build/expressions-in-makefile-preprocessing.md)