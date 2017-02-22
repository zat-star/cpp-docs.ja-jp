---
title: "LINGER 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LINGER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LINGER 構造体"
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# LINGER 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`LINGER` 構造体は `CAsyncSocket::GetSockOpt`の **SO\_LINGER** と **SO\_DONTLINGER** オプションを処理するために使用されます。  
  
## 構文  
  
```  
  
      struct linger {  
   u_short l_onoff;            // option on/off  
   u_short l_linger;           // linger time  
};  
```  
  
## 解説  
 **SO\_DONTLINGER** オプションを設定すると、送信する認識されていないデータを待っている間にメンバー関数 **閉じる** でブロックのを防ぐことができます。  このオプションを設定すると、0 に **l\_onoff** の **SO\_LINGER** を設定するのと同じ設定されている。  
  
## 必要条件  
 **ヘッダー:** winsock2.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CAsyncSocket::GetSockOpt](../Topic/CAsyncSocket::GetSockOpt.md)   
 [CAsyncSocket::SetSockOpt](../Topic/CAsyncSocket::SetSockOpt.md)