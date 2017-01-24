---
title: "Rebar コントロールでの通知メッセージの処理 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReBarCtrl クラス, 通知メッセージ (送信される)"
  - "通知, CReBarCtrl"
  - "RBN_ 通知メッセージ"
  - "RBN_ 通知メッセージ, 記述"
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Rebar コントロールでの通知メッセージの処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

rebar のコントロールの親クラスで処理したいすべての rebar コントロール \(`CReBarCtrl`\) の通知メッセージの switch ステートメントと `OnChildNotify` のハンドラー関数を作成します。  通知が親ウィンドウにユーザーが rebar のコントロールから rebar コントロールの上にオブジェクトを変更して、rebar バンドのレイアウトを削除するバンドなどをドラッグしたときに送信されます。  
  
 以下の通知メッセージは、Rebar コントロール オブジェクトによって送信できます:  
  
-   **RBN\_AUTOSIZE**は rebar コントロールのして rebar が自動的にそれ自身のサイズを変更するとされる \(**RBS\_AUTOSIZE** のスタイルと作成\)。  
  
-   **RBN\_BEGINDRAG**は rebar のコントロールでユーザーがバンドのドラッグを開始すると、される。  
  
-   **RBN\_CHILDSIZE**は rebar のコントロールによってバンドの子ウィンドウのサイズが変更されたときにされる。  
  
-   **RBN\_DELETEDBAND**は rebar のコントロールによってバンドが削除されたされる。  
  
-   **RBN\_DELETINGBAND**は rebar のコントロールによって、バンドが削除されるとされる。  
  
-   **RBN\_ENDDRAG**は rebar のコントロールでユーザーがバンドのドラッグを停止すると、される。  
  
-   **RBN\_GETOBJECT**は rebar のコントロールにオブジェクトのコントロールのバンドにドラッグすると、される \(**RBS\_REGISTERDROP** のスタイルと作成\)。  
  
-   **RBN\_HEIGHTCHANGE**は rebar のコントロールで高さが変更されたされる。  
  
-   **RBN\_LAYOUTCHANGED**は rebar コントロールの変更によって、ユーザーがコントロールのバンドのレイアウトされる。  
  
 これらの通知の詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [Rebar のコントロールの参照](http://msdn.microsoft.com/library/windows/desktop/bb774375) を参照します。  
  
## 参照  
 [CReBarCtrl の使い方](../Topic/Using%20CReBarCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)