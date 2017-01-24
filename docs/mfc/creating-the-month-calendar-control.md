---
title: "月間予定表コントロールの作成 | Microsoft Docs"
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
  - "CMonthCalCtrl クラス, 作成"
  - "月間予定表コントロール"
  - "月間予定表コントロール, 作成"
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 月間予定表コントロールの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

月間予定表コントロールがどのように作成されるかをダイアログ ボックスにコントロールを使用するか、nondialog ウィンドウで作成されるかどうかによって異なります。  
  
### CMonthCalCtrl を直接ダイアログ ボックスで使用できます。  
  
1.  ダイアログ エディターで、ダイアログ テンプレート リソースを月間予定表コントロールを追加します。  コントロール ID を指定します。  
  
2.  月間予定表コントロールのプロパティ ダイアログ ボックスを使用して、必要なスタイルを指定します。  
  
3.  コントロール プロパティを持つ型 [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md) のメンバー変数を追加するに [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md) を使用します。  `CMonthCalCtrl` のメンバー関数を呼び出すには、このメンバーを使用できます。  
  
4.  これを処理する必要がある月間予定表コントロール通知メッセージのダイアログ クラスのハンドラー関数をマップするには、プロパティ ウィンドウを使用します。[関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)を参照してください。  
  
5.  [OnInitDialog](../Topic/CDialog::OnInitDialog.md)で、`CMonthCalCtrl` オブジェクトの追加スタイルを設定します。  
  
### CMonthCalCtrl を nondialog ウィンドウで使用します。  
  
1.  ビューまたはウィンドウ クラスのコントロールを定義します。  
  
2.  \(コントロールをサブクラス化したら\) 親ウィンドウの [OnCreate](../Topic/CWnd::OnCreate.md) のハンドラー関数には早くも [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md)のコントロールの [作成](../Topic/CMonthCalCtrl::Create.md) メンバー関数を、おそらく、場合に呼び出します。  コントロールのスタイルを設定します。  
  
## 参照  
 [CMonthCalCtrl の使い方](../Topic/Using%20CMonthCalCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)