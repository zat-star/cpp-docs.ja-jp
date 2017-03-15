---
title: "文字の比較 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "文字 [C++], 比較"
  - "比較 (文字を)"
  - "MBCS [C++], 文字の比較"
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# 文字の比較
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のヒントを参考にしてください。  
  
-   既知の先行バイトと ASCII 文字との比較は正しく動作します。  
  
    ```  
    if( *sz1 == 'A' )  
    ```  
  
-   2 つの未知の文字を比較するには、Mbstring.h で定義されている次のマクロを使用します。  
  
    ```  
    if( !_mbccmp( sz1, sz2) )  
    ```  
  
     ここでは、ダブル バイト文字の両方のバイトが等しいかどうかを比較しています。  
  
## 参照  
 [MBCS のプログラミングについて](../Topic/MBCS%20Programming%20Tips.md)   
 [バッファー オーバーフロー](../text/buffer-overflow.md)