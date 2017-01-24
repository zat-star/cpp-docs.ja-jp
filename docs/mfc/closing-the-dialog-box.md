---
title: "ダイアログ ボックスのクローズ | Microsoft Docs"
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
  - "ダイアログ ボックス, 閉じる"
  - "MFC ダイアログ ボックス, 閉じる"
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ダイアログ ボックスのクローズ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

モーダル ダイアログ ボックスでは、ボタン、通常、OK ボタンとキャンセル ボタンの 1 つがを選択すると閉じます。  OK またはキャンセルをクリックすると、Windows は **IDOK** または **IDCANCEL**ダイアログ オブジェクトにボタンの ID を持つ **BN\_CLICKED** コントロール通知メッセージを送信します。  `CDialog` で これらのメッセージの既定のハンドラー関数を提供し、T: `OnOK` と `OnCancel`。  既定のハンドラーは、ダイアログ ウィンドウを閉じるに `EndDialog` メンバー関数を呼び出します。  また、独自のコードから `EndDialog` を呼び出すことができます。  詳細については、" *MFC リファレンス"の*" `CDialog` クラスの [EndDialog](../Topic/CDialog::EndDialog.md) メンバー関数を参照します。  
  
 モードレス ダイアログ ボックスは、オーバーライド `PostNcDestroy` を閉じ、削除を準備し、**this** ポインターの **delete** の演算子を呼び出す。  [Dialog Box の無効化](../Topic/Destroying%20the%20Dialog%20Box.md) は 次に何が起こるかを示しています。  
  
## 参照  
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)