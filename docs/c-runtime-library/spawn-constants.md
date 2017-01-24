---
title: "spawn 定数 | Microsoft Docs"
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
  - "_P_NOWAIT"
  - "_P_OVERLAY"
  - "_P_WAIT"
  - "_P_DETACH"
  - "_P_NOWAITO"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_P_DETACH 定数"
  - "_P_NOWAIT 定数"
  - "_P_NOWAITO 定数"
  - "_P_OVERLAY 定数"
  - "_P_WAIT 定数"
  - "P_DETACH 定数"
  - "P_NOWAIT 定数"
  - "P_NOWAITO 定数"
  - "P_OVERLAY 定数"
  - "P_WAIT 定数"
  - "spawn 定数"
ms.assetid: e0533e88-d362-46fc-b53c-5f193226d879
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# spawn 定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
#include <process.h>  
```  
  
## 解説  
 `mode` の引数はは操作の前および中に呼び出しプロセスによって実行されるアクションを決定します。  `mode` の値があります:  
  
|定数|説明|  
|--------|--------|  
|`_P_OVERLAY`|呼び出しプロセス \(`_exec` が呼び出すのと同じ\) をオーバーレイする効果を破棄する新しいプロセスと呼び出しプロセスについて説明します。|  
|`_P_WAIT`|新しいプロセスの実行が完了するまで呼び出し元スレッドを中断します \(同期 `_spawn`\)。|  
|`_P_NOWAIT`, `_P_NOWAITO`|新しいプロセス \(非同期 `_spawn`\) する呼び出しプロセスを継続します。|  
|`_P_DETACH`|呼び出しプロセスを継続します; 新しいプロセスはコンソールまたはキーボードにアクセスせずにバックグラウンドで動作します。  新しいプロセスに対する `_cwait` への呼び出しは失敗します。  これは非同期 `_spawn`です。|  
  
## 参照  
 [\_spawn 系関数と \_wspawn 系関数](../Topic/_spawn,%20_wspawn%20Functions.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)