---
title: "リッチ エディット コントロールでの文字書式の設定 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditCtrl クラス, 文字書式"
  - "書式指定 [C++], 文字"
  - "リッチ エディット コントロール, 文字書式"
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# リッチ エディット コントロールでの文字書式の設定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

書式指定文字にリッチ エディット コントロール \([CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)\) のメンバー関数を使用して、書式設定情報を取得できます。  文字に対し、斜体、Protected 太字などのタイプフェイス指定し、効果のサイズを設定し、色、できます。  
  
 [SetSelectionCharFormat](../Topic/CRichEditCtrl::SetSelectionCharFormat.md) と [SetWordCharFormat](../Topic/CRichEditCtrl::SetWordCharFormat.md) メンバー関数を使用して文字書式を適用できます。  選択したテキストの現在の文字書式を確認するには、[GetSelectionCharFormat](../Topic/CRichEditCtrl::GetSelectionCharFormat.md) メンバー関数を使用します。  これらのメンバー関数と [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) 構造体が文字属性を指定するために使用されます。  **CHARFORMAT** の重要なメンバーの 1 つが **dwMask**です。  `SetSelectionCharFormat` と `SetWordCharFormat`で、**dwMask** はどの文字属性がこの関数呼び出しで設定されるかを指定します。  `GetSelectionCharFormat` を選択範囲の最初の文字の属性を報告します; **dwMask** は選択で一貫している属性を指定します。  
  
 「既定の文字書式を取得および設定する」の後に挿入された文字に適用される書式です。  たとえば、アプリケーションが太字に書式設定する既定の文字を設定し、ユーザーが文字を入力した場合、その文字は、太字で表示されます。  既定の文字の書式設定を取得および設定するには、[GetDefaultCharFormat](../Topic/CRichEditCtrl::GetDefaultCharFormat.md) と [SetDefaultCharFormat](../Topic/CRichEditCtrl::SetDefaultCharFormat.md) メンバー関数を使用します。  
  
 「属性がテキストの外観が変更されない文字を保護します。  保護されたなテキストを変更するユーザーの操作がリッチ エディット コントロールの親ウィンドウに **EN\_PROTECTED** 通知メッセージを送信する場合は、変更を許可するか、親ウィンドウを行えるようにします。  この通知メッセージを受け取るために、[SetEventMask](../Topic/CRichEditCtrl::SetEventMask.md) メンバー関数を使用してこの機能を有効にする必要があります。  イベント マスクに関する詳細については、このトピックの [リッチ エディット コントロールからの通知](../mfc/notifications-from-a-rich-edit-control.md)を、後で参照します。  
  
 前景色は文字属性が、背景色がリッチ エディット コントロールのプロパティです。  背景色を設定するには、[SetBackgroundColor](../Topic/CRichEditCtrl::SetBackgroundColor.md) メンバー関数を使用します。  
  
## 参照  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)