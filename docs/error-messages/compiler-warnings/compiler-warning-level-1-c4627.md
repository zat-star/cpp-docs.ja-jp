---
title: "コンパイラの警告 (レベル 1) C4627 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4627"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4627"
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4627
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\<identifier\>': プリコンパイル済みヘッダーの使用を検索中にスキップされました  
  
 プリコンパイル済みヘッダーが使用されている場所を検索している間に、コンパイラが *\<identifier\>* インクルード ファイルの `#include` ディレクティブを検出しました。 コンパイラは `#include` ディレクティブを無視しますが、プリコンパイル済みヘッダーに *\<identifier\>* インクルード ファイルがまだ含まれていない場合は警告 **C4627** を発行します。  
  
## 参照  
 [プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)