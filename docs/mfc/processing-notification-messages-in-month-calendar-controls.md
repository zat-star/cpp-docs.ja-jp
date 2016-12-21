---
title: "月間予定表コントロールでの通知メッセージの処理 | Microsoft Docs"
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
  - "CMonthCalCtrl クラス, 日付状態"
  - "CMonthCalCtrl クラス, 通知"
  - "月間予定表コントロール, 通知メッセージ"
  - "通知, CMonthCalCtrl の"
  - "通知, 月間予定表コントロール"
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 月間予定表コントロールでの通知メッセージの処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユーザーが月間予定表コントロールで \(日付を選択し、別の月を表示\) を操作しているときに、コントロール \(`CMonthCalCtrl`\) が親ウィンドウ \(通常はビューまたはダイアログ オブジェクトに通知メッセージを送信します。  応答の操作を実行する場合は、このメッセージを処理してください。  たとえば、ユーザーが別の月を表示するために選択したときに表示される一連の日付を提供できます。  
  
 これを実装したいメッセージの親クラスに通知ハンドラーを追加するには、プロパティ ウィンドウを使用します。  
  
 次の一覧は月間予定表コントロールから送信された各種通知について説明します。  
  
-   **MCN\_GETDAYSTATE**は、日付を太字で表示する必要がある情報を要求します。  この通知の処理の詳細については、「[月間予定表コントロールの日の状態の設定](../mfc/setting-the-day-state-of-a-month-calendar-control.md)」を参照してください。  
  
-   **MCN\_SELCHANGE**は特定の日付または日付の範囲が変更されたことを親に通知します。  
  
-   **MCN\_SELECT**は明示日付選択が行われたことを親に通知します。  
  
## 参照  
 [CMonthCalCtrl の使い方](../Topic/Using%20CMonthCalCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)