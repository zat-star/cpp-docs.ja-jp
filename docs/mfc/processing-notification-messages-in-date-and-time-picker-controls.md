---
title: "日時指定コントロールの通知メッセージの処理 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DTN_CLOSEUP"
  - "DTN_DATETIMECHANGE"
  - "DTN_DROPDOWN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDateTimeCtrl クラス, 処理 (通知を)"
  - "DateTimePicker コントロール [MFC]"
  - "DateTimePicker コントロール [MFC], 処理 (通知を)"
  - "DTN_CLOSEUP 通知"
  - "DTN_DATETIMECHANGE 通知"
  - "DTN_DROPDOWN 通知"
  - "DTN_FORMAT 通知"
ms.assetid: ffbe29ab-ff80-4609-89f7-260b404439c4
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 日時指定コントロールの通知メッセージの処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユーザーが日時指定のコントロールと対話するように、コントロール`CDateTimeCtrl` \(\) が親ウィンドウ \(通常はビューまたはダイアログ オブジェクトに通知メッセージを送信します。  応答の操作を実行する場合は、このメッセージを処理してください。  たとえば、埋め込まれたな月間予定表コントロールを表示するためにユーザーが日時指定を開くと **DTN\_DROPDOWN** 通知が送信されます。  
  
 これを実装したいメッセージの親クラスに通知ハンドラーを追加するには、プロパティ ウィンドウを使用します。  
  
 次の一覧は日時指定のコントロールから送信された各種通知について説明します。  
  
-   **DTN\_DROPDOWN**は埋め込まれたな月間予定表コントロールが表示されることを親に通知します。  この通知は **DTS\_UPDOWN** のスタイルが設定されていないだけ送られます。  この通知詳細については、「[埋め込まれたな月間予定表コントロールのアクセス](../mfc/accessing-the-embedded-month-calendar-control.md)」を参照してください。  
  
-   **DTN\_CLOSEUP**は埋め込まれたな月間予定表コントロールが終了することを親に通知します。  この通知は **DTS\_UPDOWN** のスタイルが設定されていないだけ送られます。  
  
-   **DTN\_DATETIMECHANGE**は変更を親コントロールに発生したことを通知します。  
  
-   **DTN\_FORMAT**はテキストが必要コールバック フィールドに表示する親であることを通知します。  この通知とコールバック フィールドの詳細については、「[日時指定のコントロールのコールバック フィールドを使用します。](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)」を参照してください。  
  
-   **DTN\_FORMATQUERY**は親をコールバック フィールドに表示される文字列の最大許容サイズを指定する必要があります。  この通知を処理すると、コントロールが正しく出力を表示することができます。コントロールの表示内のちらつきを減らすことができます。  この通知詳細については、「[日時指定のコントロールのコールバック フィールドを使用します。](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)」を参照してください。  
  
-   **DTN\_USERSTRING**はユーザーが日時指定のコントロールのコンテンツの編集が完了すると、親に通知します。  この通知は **DTS\_APPCANPARSE** のスタイルが設定されている場合のみ送られます。  
  
-   **DTN\_WMKEYDOWN**は親 When コールバック フィールドのユーザー定義型を通知します。  日時指定のコントロールの非コールバック フィールドでサポートされているキーボード応答をエミュレートするために、この通知を処理してください。  この通知詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [DTP のコントロールでコールバック フィールド](http://msdn.microsoft.com/library/windows/desktop/bb761726) を参照します。  
  
## 参照  
 [CDateTimeCtrl の使い方](../mfc/using-cdatetimectrl.md)   
 [コントロール](../mfc/controls-mfc.md)