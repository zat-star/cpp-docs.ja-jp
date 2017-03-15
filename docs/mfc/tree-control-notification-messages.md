---
title: "ツリー コントロールの通知メッセージ | Microsoft Docs"
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
  - "CTreeCtrl クラス, 通知"
  - "メッセージ, 通知"
  - "通知, CTreeCtrl"
  - "通知, ツリー コントロール"
  - "ツリー コントロール, 通知メッセージ"
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ツリー コントロールの通知メッセージ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ツリー コントロール \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) は **WM\_NOTIFY** メッセージとして以下の通知メッセージ送信:  
  
|通知メッセージ|説明|  
|-------------|--------|  
|**TVN\_BEGINDRAG**|ドラッグ アンド ドロップ操作の開始を示します|  
|**TVN\_BEGINLABELEDIT**|埋め込みのラベル編集の開始を示します|  
|**TVN\_BEGINRDRAG**|マウスの右ボタンを使用して、ドラッグ アンド ドロップ操作を開始するときに、通知します|  
|**TVN\_DELETEITEM**|特定の項目の削除を通知します|  
|**TVN\_ENDLABELEDIT**|ラベル編集の終了を示します|  
|**TVN\_GETDISPINFO**|項目が表示されるようにツリー コントロールは、必要な情報を要求します。|  
|**TVN\_ITEMEXPANDED**|親項目の子アイテムの一覧を展開するか、折りたたまれたの場合|  
|**TVN\_ITEMEXPANDING**|親項目の子アイテムの一覧が展開されているか、または折りたたまれるしようとする場合|  
|**TVN\_KEYDOWN**|キーボード イベントによって通知されます。|  
|**TVN\_SELCHANGED**|選択範囲が 1 項目間で変更する場合|  
|**TVN\_SELCHANGING**|選択範囲が 1 個の項目間に変更されるという場合|  
|**TVN\_SETDISPINFO**|項目で維持される情報を更新する通知|  
  
## 参照  
 [CTreeCtrl の使い方](../Topic/Using%20CTreeCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)