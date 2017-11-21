---
title: "ATL メッセージ ハンドラーを追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- message handlers [C++]
- ATL, windows
- message handling [C++], ATL message handler
- windows [C++], ATL
- ATL, message handlers
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a30c8d2c26893ddf101d7084a91215c7ed55bf48
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="adding-an-atl-message-handler"></a>ATL メッセージ ハンドラーを追加します。
コントロールにメッセージ ハンドラー (Windows メッセージを処理するメンバー関数) を追加するに最初にクラス ビューでコントロールを選択します。 開き、**プロパティ**ウィンドウで、**メッセージ**アイコン、および反対の必須のメッセージ ボックスで、ドロップダウン リストを制御 をクリックします。 これは、コントロールのヘッダー ファイルと、コントロールの .cpp ファイルで、ハンドラーのスケルトンの実装で、メッセージ ハンドラーの宣言を追加します。 メッセージ マップを追加し、ハンドラーのエントリを追加します。  
  
 ATL でメッセージのハンドラーを追加することは、MFC クラスへのメッセージ ハンドラーの追加に似ています。 参照してください[MFC メッセージ ハンドラーを追加する](../mfc/reference/adding-an-mfc-message-handler.md)詳細についてはします。  
  
 次の条件は、ATL メッセージ ハンドラーを追加する場合にのみ適用されます。  
  
-   メッセージ ハンドラーでは、MFC と同じ名前付け規則に従います。  
  
-   新しいメッセージ マップ エントリは、メイン メッセージ マップに追加されます。 ウィザードでは、代替のメッセージ マップとの組み合わせは認識されません。  
  
## <a name="see-also"></a>関連項目  
 [ウィンドウの実装](../atl/implementing-a-window.md)

