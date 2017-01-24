---
title: "_locking 定数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_LK_RLCK"
  - "_LK_NBLCK"
  - "_LK_LOCK"
  - "_LK_NBRLCK"
  - "_LK_UNLCK"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_LK_LOCK 定数"
  - "_LK_NBLCK 定数"
  - "_LK_NBRLCK 定数"
  - "_LK_RLCK 定数"
  - "_LK_UNLCK 定数"
  - "LK_LOCK 定数"
  - "LK_NBLCK 定数"
  - "LK_NBRLCK 定数"
  - "LK_RLCK 定数"
  - "LK_UNLCK 定数"
ms.assetid: c3dc92c8-60e3-4d29-9f50-5d217627c8ad
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _locking 定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
#include <sys/locking.h>  
  
```  
  
## 解説  
 `_locking` 関数の呼び出しを mode 引数が実行されるロックのアクションを指定します。  
  
 mode 引数が次のマニフェスト定数の 1 種類があります。  
  
 `_LK_LOCK`  
 指定されたバイトをロックします。  バイトをロックする場合、関数は 1、2 番目の後でもう一度試します。  、10 の例では、バイト ロックできないと、関数の戻り値エラー。  
  
 `_LK_RLCK`  
 `_LK_LOCK` と同じ。  
  
 `_LK_NBLCK`  
 指定されたバイトをロックします。  バイトがロックした場合は、関数の戻り値エラー。  
  
 `_LK_NBRLCK`  
 `_LK_NBLCK` と同じ。  
  
 `_LK_UNLCK`  
 指定されたバイトのロックを解除します。\(バイトは前にロックされている必要があります\)。  
  
## 参照  
 [\_locking](../Topic/_locking.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)