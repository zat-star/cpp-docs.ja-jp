---
title: "CDC::SetAbortProc 用コールバック関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Callback Function for CDC::SetAbortProc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コールバック関数, CDC::SetAbortProc の"
ms.assetid: daa36d5d-15de-40fc-8d37-a865d06c4710
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# CDC::SetAbortProc 用コールバック関数
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

名前 *AbortFunc は* アプリケーションに用意された関数名のプレースホルダーです。  
  
## 構文  
  
```  
  
      BOOL CALLBACK EXPORT AbortFunc(   
   HDC hPr,   
   int code    
);  
```  
  
#### パラメーター  
 *hPr*  
 デバイス コンテキストを指定します。  
  
 `code`  
 エラーが発生したかどうかを指定します。  エラーが発生していない場合は 0 になります。  これは、アプリケーションが待機しているプリント マネージャーがディスク領域から現在はより多くのディスク容量が使用可能になると **SP\_OUTOFDISK** です。  `code` が **SP\_OUTOFDISK**の場合、アプリケーションは、印刷ジョブを中止する必要はありません。  、プリント マネージャーに **PeekMessage** または **GetMessage** Windows の関数を呼び出すことによって導入必要があります。  
  
## 戻り値  
 中止ハンドラー関数の戻り値がキャンセルされた印刷ジョブを続行する場合は 0 です 0 以外の。  
  
## 解説  
 実際の名前は [CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md)の解説セクション"に説明されているように、エクスポートする必要があります。  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md)