---
title: "ツリー コントロールの親項目と子項目 | Microsoft Docs"
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
  - "子項目 (ツリー コントロールの)"
  - "CTreeCtrl クラス, 親項目と子項目"
  - "親項目 (CTreeCtrl の)"
  - "ツリー コントロール, 親項目と子項目"
ms.assetid: abcea1e4-fe9b-40d9-86dc-1db235f8f103
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ツリー コントロールの親項目と子項目
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ツリー コントロール \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) の項目である子項目という名前が関連付けられたサブ項目のリストができます。  一つ以上の子項目を含む項目は親項目と呼ばれます。  子項目が親項目の下に表示され、表示するインデントする親への依存関係があることを示しています。  親がない項目は階層構造の最上位にあり、ルート項目と呼ばれます。  
  
 常に、親項目の子項目のリストの状態は、展開または折りたたむことができます。  状態を展開すると、子項目が親項目の下に表示されます。  これが折りたたまれると、子項目は表示されません。  リストが展開され、折りたたまれた状態のときに、ユーザーが親項目に関連付けられたボタンをクリックすると、親は **TVS\_HASBUTTONS** のスタイルが、ユーザーが親項目をダブルクリックしたときに切り替えを行いますが。  アプリケーションは [展開](../Topic/CTreeCtrl::Expand.md) メンバー関数を使用して、子項目を展開または折りたたむことができます。  
  
 ツリー コントロールに [InsertItem](../Topic/CTreeCtrl::InsertItem.md) のメンバー関数を呼び出すことにより、項目の追加をクリックします。  この関数の戻り値は、その項目を識別する **HTREEITEM** 型のハンドル。  項目を追加すると、新しい項目の親項目ハンドルを指定する必要があります。  `hParent`[TVINSERTSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb773452) 構造体またはパラメーターに親項目ハンドルの代わりに **NULL** または **TVI\_ROOT** 値を指定した場合、その項目はルート項目として追加されます。  
  
 ツリー コントロールは、親項目の子アイテムの一覧は表示されず、展開または折りたたまれると [TVN\_ITEMEXPANDING](http://msdn.microsoft.com/library/windows/desktop/bb773537) 通知メッセージを送信します。  通知は変更しないようにするか、または子項目のリストの状態に依存する親項目属性を設定することができます。  一覧の状態を変更すると、ツリー コントロールは [TVN\_ITEMEXPANDED](http://msdn.microsoft.com/library/windows/desktop/bb773533) 通知メッセージを送信します。  
  
 子項目のリストを展開すると、親項目を基準としてインデントを設定します。  [SetIndent](../Topic/CTreeCtrl::SetIndent.md) メンバー関数を使用してインデントの量を設定または [GetIndent](../Topic/CTreeCtrl::GetIndent.md) メンバー関数を使用して現在の値を取得できます。  
  
## 参照  
 [CTreeCtrl の使い方](../Topic/Using%20CTreeCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)