---
title: "MessageHandler | Microsoft Docs"
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
  - "MessageHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MessageHandler 関数"
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MessageHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**MessageHandler** により、メッセージ マップの `MESSAGE_HANDLER` マクロの 2 番目のパラメーターで識別される関数の名前です。  
  
## 構文  
  
```  
  
      LRESULT   
      MessageHandler  
      (  
   UINT uMsg,  
   WPARAM wParam,  
   LPARAM lParam,  
   BOOL& bHandled  
);  
```  
  
#### パラメーター  
 `uMsg`  
 メッセージ。  
  
 `wParam`  
 追加のメッセージ固有情報。  
  
 `lParam`  
 追加のメッセージ固有情報。  
  
 `bHandled`  
 `MessageHandler` の前の **\[真\]** へのメッセージ マップのセット `bHandled` が呼び出されます。  `MessageHandler` が完全にメッセージを処理しない限り、**FALSE** にメッセージがさらに処理する必要があることを示すために `bHandled` を設定する必要があります。  
  
## 戻り値  
 メッセージの処理の結果。  正常に終了した場合は 0。  
  
## 解説  
 メッセージ マップのこのメッセージ ハンドラーの使用例については、[MESSAGE\_HANDLER](../Topic/MESSAGE_HANDLER.md)を参照してください。  
  
## 参照  
 [ウィンドウの実装](../atl/implementing-a-window.md)   
 [メッセージ マップ](../atl/message-maps-atl.md)   
 [WM\_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)