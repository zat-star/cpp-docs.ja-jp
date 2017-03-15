---
title: "メッセージ マップ (MFC) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- message maps [C++], MFC
- Windows messages [C++], message maps
- messages [C++], Windows
- MFC [C++], messages
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: bb31d35e221c9f5d06dc34408bed500b4a18b077
ms.lasthandoff: 02/24/2017

---
# <a name="message-maps-mfc"></a>メッセージ マップ (MFC)
リファレンスのこのセクションでは、すべて一覧表示[メッセージ割り当てマクロ](../../mfc/reference/message-map-macros-mfc.md)すべて[CWnd](../../mfc/reference/cwnd-class.md)メッセージ マップ エントリと、対応するメンバー関数のプロトタイプ。  
  
|カテゴリ|説明|  
|--------------|-----------------|  
|[WM_COMMAND メッセージ ハンドラー](../../mfc/reference/wm-command-message-handler.md)|処理**WM_COMMAND**ユーザー メニュー選択またはメニュー アクセス キーによって生成されるメッセージ。|  
|[子ウィンドウの通知メッセージ ハンドラー](../../mfc/reference/child-window-notification-message-handlers.md)|子ウィンドウからの通知メッセージを処理します。|  
|[Wm _ メッセージ ハンドラー](../../mfc/reference/handlers-for-wm-messages.md)|処理**wm _ で始まる**メッセージなど、`WM_PAINT`です。|  
|[ユーザー定義メッセージ ハンドラー](../../mfc/reference/user-defined-handlers.md)|ユーザー定義メッセージを処理します。|  
  
 (用語とこのリファレンスで使用される規則の詳細については、次を参照してください[メッセージ マップ クロス リファレンスの使い方](../../mfc/reference/how-to-use-the-message-map-cross-reference.md)。)。  
  
 Windows はメッセージ指向オペレーティング システムであることが理由で、Windows 環境向けのプログラミングの大部分にはメッセージ処理が関係しています。 キーストロークやマウス クリックなどのイベントが発生するたびに、そのイベントを処理する必要があるアプリケーションに対してメッセージが送信されます。  
  
 Microsoft Foundation Class ライブラリには、メッセージベースのプログラミングに最適化されたプログラミング モデルが用意されています。 このモデルでは、特定のクラスに対してどの関数がさまざまなメッセージを処理するかを指定した "メッセージ マップ" を使用します。 メッセージ マップには、どの関数がどのメッセージを処理するかを指定する&1; つ以上のマクロが含まれています。 たとえば、`ON_COMMAND` マクロを含むメッセージ マップは、次のように記述されることがあります。  
  
 [!code-cpp[NVC_MFCMessageMaps&#16;](../../mfc/reference/codesnippet/cpp/message-maps-mfc_1.cpp)]  
  
 `ON_COMMAND` マクロは、メニュー、ボタン、およびアクセラレータ キーによって生成されるコマンド メッセージを処理するために使用します。 [マクロ](../../mfc/reference/message-map-macros-mfc.md)次をマップできます。  
  
## <a name="windows-messages"></a>Windows メッセージ  
  
-   コントロールの通知  
  
-   ユーザー定義メッセージ  
  
## <a name="command-messages"></a>コマンド メッセージ  
  
-   登録済みのユーザー定義メッセージ  
  
-   ユーザー インターフェイス更新メッセージ  
  
## <a name="ranges-of-messages"></a>メッセージの範囲  
  
-   コマンド  
  
-   ハンドラー メッセージの更新  
  
-   コントロールの通知  
  
 メッセージ マップ マクロは重要なマクロですが、通常は直接記述する必要はありません。 これは、開発者がメッセージとメッセージ処理関数を関連付けると、[プロパティ] ウィンドウでメッセージ マップ エントリがソース ファイル内に自動的に作成されるためです。 メッセージ マップ エントリは、[プロパティ] ウィンドウでいつでも編集および追加できます。  
  
> [!NOTE]
>  [プロパティ] ウィンドウでは、メッセージ マップの範囲をサポートしていません。 これらのメッセージ マップ エントリは、独自に作成する必要があります。  
  
 ただし、メッセージ マップは、Microsoft Foundation Class ライブラリの重要な部分です。 これらが何を実行するかを理解する必要があり、そのためのドキュメントが用意されています。  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


