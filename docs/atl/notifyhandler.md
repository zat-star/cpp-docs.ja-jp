---
title: "NotifyHandler | Microsoft Docs"
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
  - "NotifyHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NotifyHandler 関数"
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# NotifyHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

独自のメッセージ マップの `NOTIFY_HANDLER` マクロの 3 番目のパラメーターで識別される関数の名前。  
  
## 構文  
  
```  
  
      LRESULT   
      NotifyHandler  
      (  
   int idCtrl,  
   LPNMHDR pnmh,  
   BOOL& bHandled   
);  
```  
  
#### パラメーター  
 `idCtrl`  
 メッセージを送信するコントロールの ID。  
  
 *pnmh*  
 通知コードと追加情報を含む [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) の構造体のアドレス。  ある通知メッセージは、最初のメンバーとして **NMHDR** の構造が大きいこのパラメーターの構造体へのポインター。  
  
 `bHandled`  
 メッセージ マップでは、**\[真\]** に *NotifyHandler が* 呼び出される前に `bHandled` を設定します。  *NotifyHandler が* 完全にメッセージを処理しない限り、**FALSE** にメッセージがさらに処理する必要があることを示すために `bHandled` を設定する必要があります。  
  
## 戻り値  
 メッセージの処理の結果。  正常に終了した場合は 0。  
  
## 解説  
 メッセージ マップのこのメッセージ ハンドラーの使用例については、[NOTIFY\_HANDLER](../Topic/NOTIFY_HANDLER.md)を参照してください。  
  
## 参照  
 [ウィンドウの実装](../atl/implementing-a-window.md)   
 [メッセージ マップ](../atl/message-maps-atl.md)   
 [WM\_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)