---
title: "依存ファイルの検索パス | Microsoft Docs"
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
  - "依存, NMAKE"
  - "NMAKE プログラム, 依存"
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 依存ファイルの検索パス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

各依存ファイルには、次の構文で示されているように、省略可能な検索パスがあります。  
  
## 構文  
  
```  
{directory[;directory...]}dependent  
```  
  
## 解説  
 依存ファイルは、まず現在のディレクトリで検索され、次に指定された順序どおりにほかのディレクトリで検索されます。  マクロでは、検索パスの一部または全体を指定できます。  ディレクトリ名は中かっこ \({ }\) で囲みます。複数のディレクトリは、セミコロン \(;\) で区切ります。  空白やタブは使用できません。  
  
## 参照  
 [依存ファイル](../build/dependents.md)