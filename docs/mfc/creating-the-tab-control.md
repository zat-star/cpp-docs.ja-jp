---
title: "タブ コントロールの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TCS_EX_REGISTERDROP"
  - "TCS_EX_FLATSEPARATORS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabCtrl クラス, 作成"
  - "タブ コントロール, 作成"
  - "TCS_EX_FLATSEPARATORS 拡張スタイル"
  - "TCS_EX_REGISTERDROP 拡張スタイル"
ms.assetid: 3a9c2d64-f5f4-41ea-84ab-fceb73c3dbdc
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# タブ コントロールの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

タブ コントロールの作成方法をダイアログ ボックスにコントロールを使用するか、nondialog ウィンドウで作成されるかどうかによって異なります。  
  
### CTabCtrl を直接ダイアログ ボックスで使用できます。  
  
1.  ダイアログ エディターで、ダイアログ テンプレート リソースをタブ コントロールを追加します。  コントロール ID を指定します。  
  
2.  コントロール プロパティを持つ型 [CTabCtrl](../Topic/CTabCtrl%20Class.md) のメンバー変数を追加するに [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md) を使用します。  `CTabCtrl` のメンバー関数を呼び出すには、このメンバーを使用できます。  
  
3.  これを処理する必要があるタブ コントロールの通知メッセージのダイアログ クラス マップのハンドラー関数。  詳細については、「[関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)」を参照してください。  
  
4.  [OnInitDialog](../Topic/CDialog::OnInitDialog.md)で、`CTabCtrl`のスタイルを設定します。  
  
### CTabCtrl を nondialog ウィンドウで使用します。  
  
1.  ビューまたはウィンドウ クラスのコントロールを定義します。  
  
2.  \(コントロールをサブクラス化したら\) 親ウィンドウの [OnCreate](../Topic/CWnd::OnCreate.md) のハンドラー関数には早くも [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md)のコントロールの [作成](../Topic/CTabCtrl::Create.md) メンバー関数を、おそらく、場合に呼び出します。  コントロールのスタイルを設定します。  
  
 `CTabCtrl` オブジェクトを作成した後、次の拡張スタイルを設定またはクリアできます。:  
  
-   **TCS\_EX\_FLATSEPARATORS**はタブ項目間でタブ コントロール区分線を描画します。  この拡張スタイルは **TCS\_BUTTONS** と **TCS\_FLATBUTTONS** のスタイルを持つタブ コントロールにのみ影響します。  **TCS\_FLATBUTTONS** のスタイルでタブ コントロールを作成します既定ではこの拡張スタイルを設定します。  
  
-   **TCS\_EX\_REGISTERDROP**はタブ コントロール オブジェクトがコントロールのタブ アイテムにドラッグすると、ドロップ ターゲット オブジェクトを要求するに **TCN\_GETOBJECT** 通知メッセージを生成します。  
  
    > [!NOTE]
    >  **TCN\_GETOBJECT** 通知を受け取るには、[AfxOleInit](../Topic/AfxOleInit.md)を呼び出して OLE ライブラリを初期化しなければなりません。  
  
 これらのスタイルは [GetExtendedStyle](../Topic/CTabCtrl::GetExtendedStyle.md) と [SetExtendedStyle](../Topic/CTabCtrl::SetExtendedStyle.md) のメンバー関数への呼び出しでコントロールが作成された後で取得され、設定できます。  
  
 たとえば、次のコード行に **TCS\_EX\_FLATSEPARATORS** のスタイルを設定する:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#33](../mfc/codesnippet/CPP/creating-the-tab-control_1.cpp)]  
  
 次のコード行を持つ `CTabCtrl` オブジェクトから **TCS\_EX\_FLATSEPARATORS** のスタイルをクリアする:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#34](../mfc/codesnippet/CPP/creating-the-tab-control_2.cpp)]  
  
 これは `CTabCtrl` オブジェクトのボタンの間に表示される区切り記号を削除します。  
  
## 参照  
 [CTabCtrl の使い方](../mfc/using-ctabctrl.md)   
 [コントロール](../mfc/controls-mfc.md)