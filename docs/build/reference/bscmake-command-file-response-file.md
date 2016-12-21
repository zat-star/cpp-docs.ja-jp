---
title: "BSCMAKE コマンド ファイル (応答ファイル) | Microsoft Docs"
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
  - "BSCMAKE, コマンド ファイル"
  - "BSCMAKE, 応答ファイル"
  - "コマンド ファイル"
  - "コマンド ファイル, BSCMAKE"
  - "応答ファイル"
  - "応答ファイル, BSCMAKE"
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# BSCMAKE コマンド ファイル (応答ファイル)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コマンド ファイルでは、コマンド ライン入力の一部または全体を指定できます。  コマンド ファイルは、次の構文を使用して指定します。  
  
```  
BSCMAKE @filename  
```  
  
 コマンド ファイルは、1 つしか指定できません。  *filename* では、パスを指定できます。  *filename* の先頭には、アット マーク \(@\) を付けます。  拡張子は、必ずしも指定する必要はありません。  コマンド ラインでは、*filename* の後に追加の *sbrfiles* を指定できます。  コマンド ファイルは、コマンド ラインで指定する場合と同じ順序で BSCMAKE への入力が格納されているテキスト ファイルです。  コマンド ライン引数は、スペース、タブ、または改行文字を 1 つ以上使用して区切ります。  
  
 コマンド ファイルを使用して BSCMAKE を呼び出す場合は、次のコマンドを使用します。  
  
```  
BSCMAKE @prog1.txt  
```  
  
 サンプルのコマンド ファイルは、次のとおりです。  
  
```  
/n /v /o main.bsc /El  
/S (  
toolbox.h  
verdate.h c:\src\inc\screen.h  
)  
file1.sbr file2.sbr file3.sbr file4.sbr  
```  
  
## 参照  
 [BSCMAKE リファレンス](../../build/reference/bscmake-reference.md)