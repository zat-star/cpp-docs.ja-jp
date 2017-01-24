---
title: "_CRT_DISABLE_PERFCRIT_LOCKS | Microsoft Docs"
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
  - "_CRT_DISABLE_PERFCRIT_LOCKS"
  - "CRT_DISABLE_PERFCRIT_LOCKS"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CRT_DISABLE_PERFCRIT_LOCKS 定数"
  - "CRT_DISABLE_PERFCRIT_LOCKS 定数"
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CRT_DISABLE_PERFCRIT_LOCKS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

I\/O 操作のパフォーマンスが重要なロックを無効にします。  
  
## 構文  
  
```  
#define _CRT_DISABLE_PERFCRIT_LOCKS  
```  
  
## 解説  
 このシンボルを定義すると、すべての I\/O 操作に I\/O シングルスレッド モデルを使用するように、シングルスレッドで入力\/出力バインドされるプログラムのパフォーマンスを向上できます。  詳細については、「[マルチスレッド ライブラリのパフォーマンス](../c-runtime-library/multithreaded-libraries-performance.md)」を参照してください。  
  
## 参照  
 [グローバル定数](../c-runtime-library/global-constants.md)