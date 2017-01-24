---
title: "signal のアクション定数 | Microsoft Docs"
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
  - "SIG_IGN"
  - "SIG_DFL"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "SIG_DFL 定数"
  - "SIG_IGN 定数"
  - "signal のアクション定数"
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# signal のアクション定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

割り込み場合を受け取ったときに実行される処理は `func`の値によって決まります。  
  
## 構文  
  
```  
#include <signal.h>  
```  
  
## 解説  
 `func` の引数には、次に示すと SIGNAL.H.に定義されているマニフェスト定数関数アドレスまたは 1 個必要があります。  
  
 `SIG_DFL`  
 システムの既定の応答を使用します。  呼び出し元のプログラムがストリーム I\/O を使用した場合、ランタイム ライブラリによって作成されるバッファーがフラッシュされません。  
  
 `SIG_IGN`  
 割り込み場合は無視されます。  この値は `SIGFPE`のプロセスの浮動小数点状態を未定義のままであるため、用意されている必要があります。  
  
 `SIG_SGE`  
 コードでエラーが発生したことを示します。  
  
 `SIG_ACK`  
 受信確認を受信したことを示します。  
  
 `SIG_ERR`  
 エラーを示すシグナルの戻り値の型が発生しました。  
  
## 参照  
 [signal](../c-runtime-library/reference/signal.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)