---
title: "リスト コントロールの作成 | Microsoft Docs"
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
  - "CListCtrl クラス, creating コントロール"
  - "リスト コントロール"
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# リスト コントロールの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リスト コントロール \([CListCtrl](../Topic/CListCtrl%20Class.md)\) をどのように作成するかコントロールを直接使用するか、クラス [CListView](../mfc/reference/clistview-class.md) を使用しているかによって異なります。  `CListView`を使用している場合、フレームワークはドキュメント\/ビューの作成手順の一部としてビューを構築します。  リスト ビューを作成すると、リスト コントロールを作成します。2 は同じです\)。  コントロールは、[OnCreate](../Topic/CWnd::OnCreate.md) のハンドラー関数で作成されます。  この場合、コントロールは、[GetListCtrl](../Topic/CListView::GetListCtrl.md)呼び出しによって項目を追加できるように準備が整いました。  
  
### CListCtrl を直接ダイアログ ボックスで使用できます。  
  
1.  ダイアログ エディターで、ダイアログ テンプレート リソースをリスト コントロールを追加します。  コントロール ID を指定します。  
  
2.  コントロール プロパティを持つ型 `CListCtrl` のメンバー変数を追加するに [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md) を使用します。  `CListCtrl` のメンバー関数を呼び出すには、このメンバーを使用できます。  
  
3.  これを処理する必要があるすべてのリスト コントロールからの通知メッセージのダイアログ クラスのハンドラー関数をマップするには、プロパティ ウィンドウを使用します。[関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)を参照してください。  
  
4.  [OnInitDialog](../Topic/CDialog::OnInitDialog.md)で、`CListCtrl`のスタイルを設定します。  [変更のリスト コントロールのスタイル](../Topic/Changing%20List%20Control%20Styles.md)を参照してください。  これは「ビューの種類ビューを後で変更することができますが」、はコントロールで取得できます。  
  
### CListCtrl を nondialog ウィンドウで使用します。  
  
1.  ビューまたはウィンドウ クラスのコントロールを定義します。  
  
2.  \(コントロールをサブクラス化したら\) 親ウィンドウの [OnCreate](../Topic/CWnd::OnCreate.md) のハンドラー関数には早くも [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md)のコントロールの [作成](../Topic/CListCtrl::Create.md) メンバー関数を、おそらく、場合に呼び出します。  コントロールのスタイルを設定します。  
  
## 参照  
 [CListCtrl の使い方](../Topic/Using%20CListCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)