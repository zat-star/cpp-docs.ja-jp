---
title: "ビューを介してユーザー入力の解釈 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- interpreting user input through views [MFC]
- views [MFC], user interface and input
- input [MFC], view class [MFC]
- CView class [MFC], interpreting user input
- user input [MFC], interpreting through view class [MFC]
ms.assetid: f0302a70-661f-4781-8fe7-78f082bef2a5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 263afe7b444722174d1787594f869087d606a235
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="interpreting-user-input-through-a-view"></a>ビューを経由したユーザー入力の解釈
ビューの他のメンバー関数は、処理し、すべてのユーザー入力を解釈します。 通常、処理するビュー クラスのメッセージ ハンドラー メンバー関数を定義します。  
  
-   Windows[メッセージ](../mfc/messages.md)マウスとキーボードの操作によって生成されます。  
  
-   [コマンド](../mfc/user-interface-objects-and-command-ids.md)からメニューのツールバーのボタン、およびアクセラレータ キー。  
  
 これらのメッセージ ハンドラー メンバー関数は、データの入力、選択または編集、として、次の操作をして、クリップボードからデータの移動などを解釈します。  
  
-   マウスの動きクリック、ドラッグ、およびダブルクリック  
  
-   キー操作  
  
-   メニュー コマンド  
  
 Windows メッセージ ビューで処理は、アプリケーションのニーズによって異なります。  
  
 [メッセージの処理とマップ」](../mfc/message-handling-and-mapping.md)コマンドにメニュー項目とその他のユーザー インターフェイス オブジェクトを割り当てる方法と、コマンドをハンドラー関数にバインドする方法について説明します。 [メッセージの処理とマップ」](../mfc/message-handling-and-mapping.md)も MFC でのコマンドをルーティングする方法について説明し、それらのハンドラーを含んでいるオブジェクトの標準 Windows メッセージを送信します。  
  
 たとえば、アプリケーションは、直接的なマウス ビューの描画を実装する必要があります。 Scribble サンプルを処理する方法を示しています、 `WM_LBUTTONDOWN`、 `WM_MOUSEMOVE`、および`WM_LBUTTONUP`を開始するには、それぞれのメッセージ続行され、直線セグメントの描画を終了します。 その一方で、選択内容の表示のマウス クリックを解釈する必要がある場合があります。 ビューの`OnLButtonDown`ハンドラー関数をユーザーが描画またはを選択するかどうか確認します。 選択すると、確認ハンドラーがビュー内のオブジェクトの境界内をクリックするかどうかと、その場合は場合、は、選択したオブジェクトを表示する表示を変更します。  
  
 ビューの編集 メニューの切り取り、コピー、貼り付け、またはクリップボードを使用して、選択したデータを削除するなど、特定のメニュー コマンドの処理もできます。 このようなハンドラーは関数を呼び出すいくつかクリップボードに関連するメンバーのクラスの`CWnd`にまたはクリップボードから選択したデータ項目を転送します。  
  
## <a name="see-also"></a>参照  
 [ビューの使い方](../mfc/using-views.md)

