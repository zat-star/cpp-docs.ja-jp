---
title: "ダイアログ ボックスの有効期間 | Microsoft Docs"
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
  - "ダイアログ ボックス, 有効期間"
  - "有効期間 (ダイアログ ボックスの)"
  - "MFC ダイアログ ボックス, 有効期間"
  - "モーダル ダイアログ ボックス, 有効期間"
  - "モードレス ダイアログ ボックス, 有効期間"
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ダイアログ ボックスの有効期間
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ダイアログ ボックスのライフ サイクル中に、ユーザーはダイアログ ボックスによってダイアログ オブジェクトを作成し、初期化するコマンド ハンドラー内のダイアログ ボックスは、通常、ユーザー対話します。呼び出し、ダイアログ ボックスが閉じます。  
  
 モーダル ダイアログ ボックスでは、ハンドラーがダイアログ ボックスを閉じた後、ユーザー データを収集します。  ダイアログ ウィンドウが閉じた後ダイアログ オブジェクトがないため、データを取得するには、ダイアログ クラスのメンバー変数を使用できます。  
  
 モードレス ダイアログ ボックスでは、ダイアログ ボックスが表示されているときは、ダイアログ オブジェクトからデータを取得できます。  ある時点で、ダイアログ;オブジェクトは破棄されます。この場合、コードによって異なります。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [ダイアログ ボックスを作成し、表示します。](../mfc/creating-and-displaying-dialog-boxes.md)  
  
-   [モーダル ダイアログ ボックスの作成](../mfc/creating-modal-dialog-boxes.md)  
  
-   [モードレス ダイアログ ボックスを作成します。](../mfc/creating-modeless-dialog-boxes.md)  
  
-   [メモリ ダイアログ テンプレートを使用する](../mfc/using-a-dialog-template-in-memory.md)  
  
-   [ダイアログ ボックスの背景色を設定する](../mfc/setting-the-dialog-box’s-background-color.md)  
  
-   [ダイアログ ボックスの初期化](../mfc/initializing-the-dialog-box.md)  
  
-   [ダイアログ ボックスの Windows メッセージの処理](../mfc/handling-windows-messages-in-your-dialog-box.md)  
  
-   [ダイアログ オブジェクトからのデータの取得](../Topic/Retrieving%20Data%20from%20the%20Dialog%20Object.md)  
  
-   [ダイアログ ボックスを閉じます。](../mfc/closing-the-dialog-box.md)  
  
-   [ダイアログ ボックスの無効化](../Topic/Destroying%20the%20Dialog%20Box.md)  
  
-   [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../mfc/dialog-data-exchange-and-validation.md)  
  
-   [プロパティ シート ダイアログ ボックス](../mfc/property-sheets-and-property-pages-mfc.md)  
  
## 参照  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)