---
title: "ワイルドカードの展開 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_setargv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_setargv 関数"
  - "アスタリスク ワイルドカード"
  - "コマンド ライン, 引数の処理"
  - "コマンド ライン, ワイルドカード"
  - "コマンド ライン ワイルドカード"
  - "疑問符, ワイルドカード"
ms.assetid: 1a543398-607b-4404-93d1-45d290bde638
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ワイルドカードの展開
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 コマンド ラインでファイル名とパスの引数を指定するときに、ワイルドカード \(疑問符 \(?\) およびアスタリスク \(\*\)\) を使用できます。  
  
 コマンド ライン引数は、**\_setargv** \(またはワイド文字環境の **\_wsetargv**\) というルーチンによって処理され、既定ではワイルドカードは `argv` 文字列配列で個別の文字列に展開されません。  ワイルドカードの展開を有効にする方法の詳細については、「[ワイルドカード引数の展開](../Topic/Expanding%20Wildcard%20Arguments.md)」を参照してください。  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [main: プログラムの起動](../Topic/main:%20Program%20Startup.md)