---
title: "OnCmdMsg ハンドラー | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OnCmdMsg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コマンド ルーティング, OnCmdMsg ハンドラー"
  - "ハンドラー"
  - "ハンドラー, OnCmdMessage"
  - "メッセージ, ルーティング"
  - "OnCmdMessage メソッド"
ms.assetid: 8df07024-506f-47e7-bba9-1c3bc5ad8ab6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# OnCmdMsg ハンドラー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コマンドのルーティングを行うには、各コマンドの対象は、シーケンスにおける次のコマンドの対象の `OnCmdMsg` メンバー関数を呼び出します。  それを処理できない場合は、コマンドを処理し、別のコマンド ターゲットにルーティングしてもらうかどうかをコマンドの対象の使用 `OnCmdMsg`。  
  
 各コマンドターゲット クラスは `OnCmdMsg` のメンバー関数をオーバーライドする必要があります。  オーバーライドは、クラスが特定の次の対象にコマンドをルーティングするようにようにします。  フレーム ウィンドウは、テーブル [標準コマンド ルーティング](../mfc/command-routing.md)のように現在の子ウィンドウまたはビューにコマンドを、常にルーティングします。  
  
 `OnCmdMsg` の既定の `CCmdTarget` の実装では、標準のメッセージを検索する各受信コマンド メッセージに対するハンドラー関数の検索にコマンドターゲット クラスのメッセージ マップを使用して同じです。  一致する文字列が見つかった場合、ハンドラーを呼び出します。  メッセージの検索は [フレームワークがメッセージ マップを検索します。](../mfc/how-the-framework-searches-message-maps.md)で説明します。  
  
## 参照  
 [フレームワークがハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)