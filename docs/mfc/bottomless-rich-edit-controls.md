---
title: "自動的にサイズ調整されるリッチ エディット コントロール | Microsoft Docs"
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
  - "自動的にサイズ調整されるリッチ エディット コントロール"
  - "CRichEditCtrl クラス, 自動的にサイズ調整される"
  - "リッチ エディット コントロール, 自動的にサイズ調整される"
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 自動的にサイズ調整されるリッチ エディット コントロール
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アプリケーションは、常にコンテンツと同じサイズになるようにためリッチ エディット コントロール \([CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)\) のサイズを変更できます。  リッチ エディット コントロールが親ウィンドウに [EN\_REQUESTRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787983) 通知メッセージを送信して、コンテンツのサイズが変更されるたびにこのいわゆる「ボトムレス」機能をサポートしています。  
  
 **EN\_REQUESTRESIZE** の通知メッセージを処理する場合、アプリケーションは [REQRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787950) の指定された構造体の次元にコントロールのサイズを変更する必要があります。  アプリケーションでは、コントロールで高さの制御変更に合わせてリソースが移動する場合があります。  コントロールのサイズを変更するには、`CWnd` 関数 [SetWindowPos](../Topic/CWnd::SetWindowPos.md)を使用できます。  
  
 [RequestResize](../Topic/CRichEditCtrl::RequestResize.md) メンバー関数を使用して **EN\_REQUESTRESIZE** 通知メッセージを送信するようにボトムレス リッチ エディット コントロールを強制できます。  このメッセージは [OnSize](../Topic/CWnd::OnSize.md) ハンドラーに便利です。  
  
 **EN\_REQUESTRESIZE** 通知メッセージを受け取るために、`SetEventMask` メンバー関数を使用して通知を有効にする必要があります。  
  
## 参照  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)