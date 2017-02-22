---
title: "致命的なエラー C1852 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1852"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1852"
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 致命的なエラー C1852
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'filename' は有効なプリコンパイル済みヘッダー ファイルではありません  
  
 ファイルはプリコンパイル済みヘッダーではありません。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  **\/Yu** または **\#pragma hdrstop** で指定された無効なファイル。  
  
2.  特に指定がない場合、コンパイラはファイル拡張子を .pch と想定します。