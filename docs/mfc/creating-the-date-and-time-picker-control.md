---
title: "日時指定コントロールの作成 | Microsoft Docs"
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
  - "CDateTimeCtrl クラス, 作成"
  - "DateTimePicker コントロール [MFC], 作成"
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 日時指定コントロールの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

日時指定のコントロールがどのように作成されるかをダイアログ ボックスにコントロールを使用するか、nondialog ウィンドウで作成されるかどうかによって異なります。  
  
### CDateTimeCtrl を直接ダイアログ ボックスで使用できます。  
  
1.  ダイアログ エディターで、ダイアログ テンプレート リソースを日時指定のコントロールを追加します。  コントロール ID を指定します。  
  
2.  日時指定のコントロールのプロパティ ダイアログ ボックスを使用して、必要なスタイルを指定します。  
  
3.  コントロール プロパティを持つ型 [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md) のメンバー変数を追加するに [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md) を使用します。  `CDateTimeCtrl` のメンバー関数を呼び出すには、このメンバーを使用できます。  
  
4.  これを処理する必要があるコントロールの指定 [通知](../mfc/processing-notification-messages-in-date-and-time-picker-controls.md)、DateTime のメッセージのダイアログ クラスのハンドラー関数をマップするには、プロパティ ウィンドウを使用します。[関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)を参照してください。  
  
5.  [OnInitDialog](../Topic/CDialog::OnInitDialog.md)で、`CDateTimeCtrl` オブジェクトの追加スタイルを設定します。  
  
### CDateTimeCtrl を nondialog ウィンドウで使用します。  
  
1.  ビューまたはウィンドウ クラスのコントロールを宣言します。  
  
2.  \(コントロールをサブクラス化したら\) 親ウィンドウの [OnCreate](../Topic/CWnd::OnCreate.md) のハンドラー関数には早くも [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md)のコントロールの [作成](../Topic/CTabCtrl::Create.md) メンバー関数を、おそらく、場合に呼び出します。  コントロールのスタイルを設定します。  
  
## 参照  
 [CDateTimeCtrl の使い方](../mfc/using-cdatetimectrl.md)   
 [コントロール](../mfc/controls-mfc.md)