---
title: "拡張コンボ ボックス コントロールの作成 | Microsoft Docs"
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
  - "CComboBoxEx クラス, 作成 (拡張コンボ ボックス コントロールを)"
  - "拡張コンボ ボックス"
  - "拡張コンボ ボックス, 作成"
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 拡張コンボ ボックス コントロールの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

拡張コンボ ボックスのコントロールがどのように作成されるかをダイアログ ボックスにコントロールを使用するか、nondialog ウィンドウで作成されるかどうかによって異なります。  
  
### CComboBoxEx を直接ダイアログ ボックスで使用できます。  
  
1.  ダイアログ エディターで、ダイアログ テンプレート リソースを拡張コンボ ボックスのコントロールを追加します。  コントロール ID を指定します。  
  
2.  拡張コンボ ボックスのコントロールのプロパティ ダイアログ ボックスを使用して、必要なスタイルを指定します。  
  
3.  コントロール プロパティを持つ型 [CComboBoxEx](../mfc/reference/ccomboboxex-class.md) のメンバー変数を追加するに [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md) を使用します。  `CComboBoxEx` のメンバー関数を呼び出すには、このメンバーを使用できます。  
  
4.  これを処理する必要がある拡張コンボ ボックス コントロール通知メッセージのダイアログ クラスのハンドラー関数をマップするには、プロパティ ウィンドウを使用します。[関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)を参照してください。  
  
5.  [OnInitDialog](../Topic/CDialog::OnInitDialog.md)で、`CComboBoxEx` オブジェクトの追加スタイルを設定します。  
  
### CComboBoxEx を nondialog ウィンドウで使用します。  
  
1.  ビューまたはウィンドウ クラスのコントロールを定義します。  
  
2.  親ウィンドウの [OnCreate](../Topic/CWnd::OnCreate.md) のハンドラー関数には早くも [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md)のコントロールの [作成](../Topic/CTabCtrl::Create.md) メンバー関数を、おそらく、場合に呼び出します。  コントロールのスタイルを設定します。  
  
## 参照  
 [CComboBoxEx の使い方](../mfc/using-ccomboboxex.md)   
 [コントロール](../mfc/controls-mfc.md)