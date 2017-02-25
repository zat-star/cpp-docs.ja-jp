---
title: "DHtmlUrlEventMapEntry 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DHtmlUrlEventMapEntry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DHtmlUrlEventMapEntry 構造体"
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# DHtmlUrlEventMapEntry 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`DHtmlUrlEventMapEntry` 構造体は、複数の URL イベント マップをサポートします。  
  
## 構文  
  
```  
  
      struct DHtmlUrlEventMapEntry  
{  
   LPCTSTR szUrl;  
   const DHtmlEventMapEntry *pEventMap;  
};  
```  
  
#### パラメーター  
 `szUrl`  
 URL。  
  
 *pEventMap*  
 URL に関連付けられたイベント マップ。  
  
## 必要条件  
 **ヘッダー :** afxdhtml.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)