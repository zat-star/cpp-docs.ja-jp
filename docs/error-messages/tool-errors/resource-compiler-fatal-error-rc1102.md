---
title: "リソース コンパイラの致命的なエラー RC1102 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC1102"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1102"
ms.assetid: bd2091f8-ef5e-4151-a8d6-98043e9422b6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# リソース コンパイラの致命的なエラー RC1102
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

internal error : too many arguments to RCPP  
  
 リソース コンパイラのプリプロセッサに渡された引数の数が多すぎます。  \[シンボルの定義\] オプション \(\/d オプション\) で行っているシンボル定義をソース ファイル内に移して、オプションで定義するシンボルの数を減らしてください。  このエラーは、\[INCLUDE の検索パスの追加\] オプション \(\/i オプション\) で指定したインクルード ファイルの検索パスが多すぎたときにも発生します。