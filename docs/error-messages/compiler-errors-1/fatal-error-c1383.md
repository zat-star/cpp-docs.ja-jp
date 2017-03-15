---
title: "致命的なエラー C1383 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1383"
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 致命的なエラー C1383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラ オプション \/GL は、インストールされた共通言語ランタイムのバージョンと互換性がありません  
  
 C1383 は、共通言語ランタイムの以前のバージョンをそれより新しいコンパイラで使用しているときに、**\/clr** と **\/GL.** を指定してコンパイルすると発生します。  
  
 解決するには、**\/GL** を **\/clr** と共に使用しないようにするか、使用しているコンパイラに付属している共通言語ランタイムのバージョンをインストールします。  
  
 詳細については、[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md) および [\/GL \(プログラム全体の最適化\)](../../build/reference/gl-whole-program-optimization.md) を参照してください。