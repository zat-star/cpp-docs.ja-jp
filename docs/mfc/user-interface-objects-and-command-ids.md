---
title: "ユーザー インターフェイス オブジェクトとコマンド ID | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "コマンド処理, ユーザー インターフェイス オブジェクト"
  - "コマンド ID, ユーザー インターフェイス オブジェクト"
  - "コマンド ルーティング, MFC"
  - "ショートカット キー, 関連付け (ID への)"
  - "メニュー項目, 関連付け (ID への)"
  - "MFC, コマンド ルーティング"
  - "ツール バー コントロール [MFC], コマンド ID"
  - "ユーザー インターフェイス オブジェクト, 関連付け (ID への)"
ms.assetid: 4ea19e9b-ed1e-452e-bd33-7f509107a45b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ユーザー インターフェイス オブジェクトとコマンド ID
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

メニュー項目やツール バー ボタンとアクセラレータ キーはコマンドを生成できる「ユーザー インターフェイス オブジェクト」です。  そのような各ユーザー インターフェイス オブジェクトには id を指定します。  コマンドとオブジェクトとコマンドに同じ ID を割り当てることにより、ユーザー インターフェイス オブジェクトを関連付けます。  [メッセージ](../mfc/messages.md)"で説明しているように、特別なメッセージとして実装されます。  図では、「表示でフレームワークでフレームワークがコマンドの管理方法」を参照してください。  ユーザー インターフェイス オブジェクトを作成すると、そのコマンドは、`ID_EDIT_CLEAR_ALL`など、アプリケーション オブジェクトの 1 つがコマンドを処理します、ドキュメント オブジェクトの `OnEditClearAll` 関数はドキュメントのメッセージ マップによって—下の図に…呼び出されます。  
  
 ![フレームワークにおけるコマンド](../mfc/media/vc385p1.gif "vc385P1")  
フレームワーク内のコマンド  
  
 MFC は、メニュー項目とツール バー ボタンなどのユーザー インターフェイス オブジェクトをどのように更新するか図「表示でフレームワークの」更新するコマンド。  中のドロップダウン メニューの前、またはツール バー ボタンの場合はアイドル ループ、MFC は更新コマンドをルーティングします。  次の図は、ドキュメント オブジェクトは、ユーザー インターフェイス オブジェクトを有効または無効にするように更新コマンド ハンドラー、`OnUpdateEditClearAll`、照会します。  
  
 ![フレームワークでのコマンド更新](../Image/vc385P2.png "vc385P2")  
フレームワーク内のコマンド更新  
  
## 参照  
 [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)