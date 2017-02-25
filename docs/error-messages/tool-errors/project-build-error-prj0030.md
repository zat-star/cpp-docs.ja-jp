---
title: "プロジェクト ビルド エラー PRJ0030 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0030"
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# プロジェクト ビルド エラー PRJ0030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マクロ拡張エラーです。レベル 32 を超える $\(macro\) の再帰呼び出しを評価します。  
  
 このエラーは、マクロ内の再帰によって発生します。  たとえば、**\[中間ディレクトリ\]** プロパティ \(「[&#91;全般&#93; プロパティ ページ \(プロジェクト\)](../Topic/General%20Property%20Page%20\(Project\).md)」を参照\) に $\(IntDir\) を設定した場合、再帰が発生します。  
  
 このエラーを解決するには、マクロまたはプロパティを定義するときに、そのマクロまたはプロパティを定義の中で使用しているマクロを使用しないでください。