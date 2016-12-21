---
title: "メッセージ マップ (MFC) | Microsoft Docs"
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
  - "vc.mfc.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "メッセージ マップ [C++], MFC"
  - "メッセージ [C++], Windows"
  - "MFC [C++], メッセージ"
  - "Windows メッセージ [C++], メッセージ マップ"
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# メッセージ マップ (MFC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リファレンスのこのセクションでは、すべての[メッセージ マップ マクロ](../../mfc/reference/message-map-macros-mfc.md)とすべての [CWnd](../Topic/CWnd%20Class.md) メッセージ マップ エントリを、対応するメンバー関数のプロトタイプと共に示します。  
  
|分類|説明|  
|--------|--------|  
|[WM\_COMMAND メッセージ ハンドラー](../Topic/WM_COMMAND%20Message%20Handler.md)|ユーザーのメニュー選択またはメニューのアクセス キーによって生成される **WM\_COMMAND** メッセージを処理します。|  
|[子ウィンドウの通知メッセージ ハンドラー](../Topic/Child%20Window%20Notification%20Message%20Handlers.md)|子ウィンドウからの通知メッセージを処理します。|  
|[WM\_ メッセージ ハンドラー](../../mfc/reference/handlers-for-wm-messages.md)|`WM_PAINT` のような **WM\_** メッセージを処理します。|  
|[ユーザー定義メッセージ ハンドラー](../Topic/User-Defined%20Handlers.md)|ユーザー定義メッセージを処理します。|  
  
 \(このリファレンスで使用される用語と規則の詳細については、["How to Use the Message Map Cross\-Reference \(メッセージ マップ クロス リファレンスの使い方\)"](../../mfc/reference/how-to-use-the-message-map-cross-reference.md) を参照してください\)。  
  
 Windows はメッセージ指向オペレーティング システムであることが理由で、Windows 環境向けのプログラミングの大部分にはメッセージ処理が関係しています。  キーストロークやマウス クリックなどのイベントが発生するたびに、そのイベントを処理する必要があるアプリケーションに対してメッセージが送信されます。  
  
 Microsoft Foundation Class ライブラリには、メッセージベースのプログラミングに最適化されたプログラミング モデルが用意されています。  このモデルでは、特定のクラスに対してどの関数がさまざまなメッセージを処理するかを指定した "メッセージ マップ" を使用します。  メッセージ マップには、どの関数がどのメッセージを処理するかを指定する 1 つ以上のマクロが含まれています。  たとえば、`ON_COMMAND` マクロを含むメッセージ マップは、次のように記述されることがあります。  
  
 [!code-cpp[NVC_MFCMessageMaps#16](../../mfc/reference/codesnippet/CPP/message-maps-mfc_1.cpp)]  
  
 `ON_COMMAND` マクロは、メニュー、ボタン、およびアクセラレータ キーによって生成されるコマンド メッセージを処理するために使用します。  ["Macros \(マクロ\)"](../../mfc/reference/message-map-macros-mfc.md) は、次のものをマップする目的で使用できます。  
  
## Windows メッセージ  
  
-   コントロールの通知  
  
-   ユーザー定義メッセージ  
  
## コマンド メッセージ  
  
-   登録済みのユーザー定義メッセージ  
  
-   ユーザー インターフェイス更新メッセージ  
  
## メッセージの範囲  
  
-   コマンド  
  
-   ハンドラー メッセージの更新  
  
-   コントロールの通知  
  
 メッセージ マップ マクロは重要なマクロですが、通常は直接記述する必要はありません。  これは、開発者がメッセージとメッセージ処理関数を関連付けると、\[プロパティ\] ウィンドウでメッセージ マップ エントリがソース ファイル内に自動的に作成されるためです。  メッセージ マップ エントリは、\[プロパティ\] ウィンドウでいつでも編集および追加できます。  
  
> [!NOTE]
>  \[プロパティ\] ウィンドウでは、メッセージ マップの範囲をサポートしていません。  これらのメッセージ マップ エントリは、独自に作成する必要があります。  
  
 ただし、メッセージ マップは、Microsoft Foundation Class ライブラリの重要な部分です。  これらが何を実行するかを理解する必要があり、そのためのドキュメントが用意されています。  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)