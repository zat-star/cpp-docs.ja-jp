---
title: "ツリー コントロールのラベルの編集 | Microsoft Docs"
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
  - "CTreeCtrl クラス, 編集 (ラベルを)"
  - "編集 (ツリー コントロールのラベルを)"
  - "ラベル編集 (CTreeCtrl クラスでの)"
  - "ツリー コントロール, ラベル編集"
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ツリー コントロールのラベルの編集
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユーザーは直接 **TVS\_EDITLABELS** のスタイルがあるツリー コントロール \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) に項目のラベルを編集できます。  ユーザーは、フォーカスがある項目のラベルをクリックして編集します。  アプリケーションは [EditLabel](../Topic/CTreeCtrl::EditLabel.md) メンバー関数を使用して編集します。  ツリー コントロールは、編集が開始されると、取り消されるか完了時に通知を送信します。  編集が完了すると、必要に応じて、項目のラベルの更新を管理します。  
  
 ラベル編集が始まると、ツリー コントロールの送信 [TVN\_BEGINLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773506) 通知メッセージ。  この通知を処理することにより、既存のラベルの編集を許可し、他の編集を防ぐことができます。  0 を返すことを行うことができます 0 以外のなに戻ることはできません。  
  
 ラベル編集が取り消されるか完了したら、ツリー コントロールの送信 [TVN\_ENDLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773515) 通知メッセージ。  `lParam` パラメーターは [NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418) 構造体のアドレスです。  **アイテム** のメンバーは項目を識別し、編集したテキストを含む [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) 構造です。  更新、が編集された文字列を確認した後に応じてを項目のラベルを担当します。  `TV_ITEM` の **pszText** のメンバーが編集が取り消された場合は 0 になります。  
  
 [TVN\_BEGINLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773506) 通知メッセージへの応答とラベル編集中、通常、[GetEditControl](../Topic/CTreeCtrl::GetEditControl.md) メンバー関数を使用してラベル編集に使用するエディット コントロールへのポインターを取得できます。  ユーザーがエディット コントロールに入力するか、または無効な文字を受け取り、破棄するにサブクラス化するできるテキストの量を制限するエディット コントロールの [SetLimitText](../Topic/CEdit::SetLimitText.md) のメンバー関数を呼び出すことができます。  ただし、**TVN\_BEGINLABELEDIT** が送信された後にエディット コントロールが表示されることがあります。  
  
## 参照  
 [CTreeCtrl の使い方](../Topic/Using%20CTreeCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)