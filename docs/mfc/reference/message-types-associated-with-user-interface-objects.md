---
title: "メッセージの種類のユーザー インターフェイス オブジェクトに関連付けられている |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.uiobject.msgs
dev_langs:
- C++
helpviewer_keywords:
- message types and user interface objects [MFC]
ms.assetid: 681ee1a7-f6e6-4ea0-9fc6-1fb53a35516e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ff4c7aac0c73406503df2f2384249279d3d7f97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="message-types-associated-with-user-interface-objects"></a>ユーザー インターフェイス オブジェクトに関連付けられたメッセージ
次の表は、使用する次の操作を実行する、オブジェクトの種類とそれらに関連付けられたメッセージの種類を示します。  
  
### <a name="user-interface-objects-and-associated-messages"></a>ユーザー インターフェイス オブジェクトおよび関連するメッセージ  
  
|オブジェクト ID|メッセージ|  
|---------------|--------------|  
|格納先ウィンドウを表す、クラス名|対応する Windows メッセージ、 [CWnd](../../mfc/reference/cwnd-class.md)-派生クラス: ダイアログ ボックス、ウィンドウ、子ウィンドウ、MDI 子ウィンドウ、または最上位のフレーム ウィンドウです。|  
|メニューまたはアクセラレータの識別子|-   **コマンド**メッセージ (プログラム関数を実行) します。<br />-   **UPDATE_COMMAND_UI**メッセージ (メニュー項目を動的に更新) します。|  
|コントロール id|選択したコントロールの種類の通知メッセージを制御します。|  
  
## <a name="see-also"></a>参照  
 [関数へのメッセージの割り当てください。](../../mfc/reference/mapping-messages-to-functions.md)   
 [コード ウィザードによる機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../../ide/adding-a-class-visual-cpp.md)   
 [メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)   
 [仮想関数のオーバーライド](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へ](../../ide/navigating-the-class-structure-visual-cpp.md)
