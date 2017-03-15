---
title: "ファイル名分割構文 | Microsoft Docs"
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
  - "ファイル名分割構文 (NMAKE の)"
  - "NMAKE プログラム, 構文"
  - "構文, ファイル名分割"
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# ファイル名分割構文
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コマンドのファイル名分割構文は、最初の依存ファイル名 \(明示的に指定していない依存ファイルの場合もあります\) の構成要素を表します。  ファイル名の構成要素は、ディスク上に存在するものではなく、指定されたドライブ、パス、ベース名、および拡張子です。  完全なファイル名を表すには、**%s** を使用します。  ファイル名の構成要素を表すには、**%&#124;**\[*parts*\]**F** \(縦棒がパーセント記号に後続する\) を使用します。*parts* には、次の文字を任意の順序で 0 個以上指定できます。  
  
|文字|説明|  
|--------|--------|  
|文字なし|完全名 \(**%s** と同じ\)|  
|**d**|ドライブ|  
|**p**|パス|  
|**f**|ファイルのベース名|  
|**e**|\[ファイル拡張子\]|  
  
 たとえば、ファイル名が c:\\prog.exe の場合は、次のようになります。  
  
-   %s は c:\\prog.exe です。  
  
-   %&#124;F は c:\\prog.exe です。  
  
-   %&#124;dF は c です。  
  
-   %&#124;pF は c:\\ です。  
  
-   %&#124;fF は prog です。  
  
-   %&#124;eF は exe です。  
  
## 参照  
 [メイクファイルのコマンド](../build/commands-in-a-makefile.md)