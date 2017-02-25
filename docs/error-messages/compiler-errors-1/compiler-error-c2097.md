---
title: "コンパイラ エラー C2097 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2097"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2097"
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C2097
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

初期化が正しく行われていません。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  定数ではない値での変数の初期化  
  
2.  long アドレスでの short アドレスの初期化  
  
3.  **\/Za** オプションを指定してコンパイルしているときの、定数でない式でのローカルな構造体、共用体、配列の初期化  
  
4.  コンマ演算子を含む式での初期化  
  
5.  定数でもシンボルでもない式での初期化