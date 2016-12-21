---
title: "ツリー コントロールの使い方 | Microsoft Docs"
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
  - "CTreeCtrl クラス, 使用"
  - "ツリー コントロール, ツリー コントロールの概要"
ms.assetid: 4e92941a-e477-4fb1-b1ce-4abeafbef1c1
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ツリー コントロールの使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ツリー コントロール \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) の一般的な使用法がパターンに従います。:  
  
-   コントロールが作成されます。  コントロールをダイアログ ボックス テンプレートで指定されたか、`CTreeView`を使用すると、構築がダイアログ ボックスまたはビューの作成時に自動的に行われます。  他のウィンドウの子ウィンドウとしてツリー コントロールを作成する場合は [作成](../Topic/CTreeCtrl::Create.md) メンバー関数を使用します。  
  
-   ツリー コントロールにイメージを使用する場合は [SetImageList](../Topic/CTreeCtrl::SetImageList.md)を呼び出してイメージ リストを設定します。  また [SetIndent](../Topic/CTreeCtrl::SetIndent.md)を呼び出してインデントを変更できます。  これを行うことも、[OnInitDialog](../Topic/CDialog::OnInitDialog.md) \(ダイアログ ボックスのコントロールの場合\) または [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) です \(ビューの場合\)。  
  
-   各データ項目に対して `CTreeCtrl`[InsertItem](../Topic/CTreeCtrl::InsertItem.md) 関数を呼び出すことによって、コントロールにデータを送信します。  `InsertItem` は、後で参照するために使用できる項目に子アイテムを追加するときなど、ハンドルを返します。  データを初期化することも、`OnInitDialog` \(ダイアログ ボックスのコントロールの場合\) または `OnInitialUpdate` です \(ビューの場合\)。  
  
-   ユーザーがコントロールと対話しているため、各種通知メッセージを送信します。  ユーザーがコントロール ウィンドウのメッセージ マップの **ON\_NOTIFY\_REFLECT** マクロを追加するか、親ウィンドウのメッセージ マップ `ON_NOTIFY` マクロを追加することによって処理したいの各メッセージを処理するための関数を指定できます。  有効な通知の一覧は、このトピックの [ツリー コントロールの通知メッセージ](../mfc/tree-control-notification-messages.md) "を参照してください。  
  
-   コントロールの設定値にさまざまな構成メンバー関数を呼び出します。  インデントを設定し、項目に関連付けられたテキスト、イメージ、またはデータの変更を含むように適用できる変更します。  
  
-   さまざまなコントロールの内容を調べるために、Get 関数を使用します。  また、指定された項目の親、子、兄弟へのハンドルを取得するように関数のツリー コントロールのコンテンツをスキャンできます。  特定のノードの子を並べ替えることができます。  
  
-   コントロールによってレンダリングされると、確認、正しく破棄されることを確認します。  ツリー コントロールがダイアログ ボックス内にある場合、またはビューの場合、`CTreeCtrl` オブジェクトは自動的に破棄されます。  そうでない場合、確認する必要があります `CTreeCtrl` コントロールおよびオブジェクトの両方が適切に破棄することができます。  
  
## 参照  
 [CTreeCtrl の使い方](../Topic/Using%20CTreeCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)