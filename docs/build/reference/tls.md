---
title: "/TLS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/TLS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/TLS dumpbin オプション"
  - "-TLS dumpbin オプション"
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /TLS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

実行可能ファイルの IMAGE\_TLS\_DIRECTORY 構造体を表示します。  
  
## 解説  
 \/TLS では、TLS コールバック関数のアドレスだけでなく、TLS 構造体のフィールドも表示されます。  
  
 プログラムでスレッド ローカル ストレージを使用しない場合、そのイメージには TLS 構造体は含まれません。詳細については、「[スレッド](../../cpp/thread.md)」を参照してください。  
  
 IMAGE\_TLS\_DIRECTORY は winnt.h で定義されます。  
  
## 参照  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)