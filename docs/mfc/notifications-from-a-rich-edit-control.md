---
title: "リッチ エディット コントロールからの通知メッセージ | Microsoft Docs"
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
  - "CRichEditCtrl クラス, 通知"
  - "メッセージ, 通知"
  - "通知, CRichEditCtrl から"
  - "リッチ エディット コントロール, 通知"
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# リッチ エディット コントロールからの通知メッセージ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

通知メッセージはリッチ エディット コントロール \([CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)\) に影響するイベントを報告します。  これらは、リッチ エディット コントロール自体または親ウィンドウ、メッセージ リフレクションを使用して操作できます。  リッチ エディット コントロールは、エディット コントロール、および複数の追加の使用と通知メッセージをすべてサポートしています。  」かを通知メッセージをリッチ エディット コントロールが「イベント マスクの設定による親ウィンドウに送信するかを判断できます。  
  
 リッチ エディット コントロールのイベント マスクを設定するには、[SetEventMask](../Topic/CRichEditCtrl::SetEventMask.md) メンバー関数を使用します。  [GetEventMask](../Topic/CRichEditCtrl::GetEventMask.md) メンバー関数を使用してリッチ エディット コントロールの現在のイベント マスクを取得できます。  
  
 次の段落は、いくつかの特定の通知と使用されます。:  
  
-   **EN\_MSGFILTER** の通知を処理する**EN\_MSGFILTER**はクラス、リッチ エディット コントロールを使用してまたは親ウィンドウ コントロールには、すべてのキーボード入力とマウス入力をフィルター処理します。  ハンドラーはメッセージを変更できるキーボードまたはマウス メッセージを防ぐこと、または指定 [MSGFILTER](http://msdn.microsoft.com/library/windows/desktop/bb787936) の構造を変更することで処理することができます。  
  
-   **EN\_PROTECTED**ハンドルのユーザーが保護されたなテキストを変更しようとしたことを検出する **EN\_PROTECTED** 通知メッセージ。  protected とテキストの範囲を指定するには、保護されたな文字効果を設定できます。  詳細については、「[リッチ エディット コントロールの文字書式](../mfc/character-formatting-in-rich-edit-controls.md)」を参照してください。  
  
-   **EN\_DROPFILES** ユーザーが **EN\_DROPFILES** の通知メッセージを処理するリッチ エディット コントロールにファイルをドロップできるようにすることができます。  [ENDROPFILES](http://msdn.microsoft.com/library/windows/desktop/bb787895) の構造を指定するファイルに関する情報が含まれます。  
  
-   **EN\_SELCHANGE**アプリケーションは、現在の選択範囲に **EN\_SELCHANGE** の通知メッセージを処理することにより、変更を検出できます。  通知メッセージは新しい選択の [SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb787952) を含む構造体の情報を指定します。  
  
## 参照  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)