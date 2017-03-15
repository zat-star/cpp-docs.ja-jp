---
title: "ダイアログ ボックスの実装 | Microsoft Docs"
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
  - "ATL, ダイアログ ボックス"
  - "CAxDialogImpl クラス, 実装 (ATL のダイアログ ボックスを)"
  - "CSimpleDialog クラス, 実装 (ATL のダイアログ ボックスを)"
  - "ダイアログ ボックス, ATL"
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ダイアログ ボックスの実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL プロジェクトにダイアログ ボックスを追加する方法は 2 つあります: ATL ダイアログ ウィザードを使用するか、それを手動で追加します。  
  
## ATL ダイアログ ウィザードを使用したダイアログ ボックスの追加  
 [クラスの追加&#93;ダイアログ ボックス](../ide/add-class-dialog-box.md)で、ATL プロジェクトにダイアログ ボックスを追加するために ATL ダイアログ オブジェクトを選択します。  をクリック **\[完了\]**適切として ATL ダイアログ ウィザードを入力します。  ウィザードは [CAxDialogImpl](../Topic/CAxDialogImpl%20Class.md) から派生したクラスをプロジェクトに追加します。  **\[表示\]** のメニューの\[リソース ビューを開き、ダイアログを見つけ、リソース エディターで開きます。をダブルクリックします。  
  
> [!NOTE]
>  ダイアログ ボックスに `CAxDialogImpl`から派生している場合、ActiveX コントロールと Windows 両方のコントロールをホストできます。  ダイアログ ボックスのクラスの ActiveX コントロールのサポートのオーバーヘッドが不要な場合は、[CSimpleDialog](../atl/reference/csimpledialog-class.md) か [CDialogImpl](../Topic/CDialogImpl%20Class.md) を使用します。  
  
 メッセージとイベント ハンドラーは、クラス ビューから、ダイアログ クラスに追加できます。  詳細については、「[ATL メッセージ ハンドラーの追加](../atl/adding-an-atl-message-handler.md)」を参照してください。  
  
## ダイアログ ボックスを手動で追加します  
 ダイアログ ボックスを実装すると、ペインの実装に似ています。  [CAxDialogImpl](../Topic/CAxDialogImpl%20Class.md)、[CDialogImpl](../Topic/CDialogImpl%20Class.md)、または [CSimpleDialog](../atl/reference/csimpledialog-class.md) からクラスを派生し、メッセージに [メッセージ マップ](../atl/message-maps-atl.md) を宣言します。  ただし、の派生クラスでダイアログ テンプレート リソースの ID を指定する必要があります。  このクラスは、この値を保持する `IDD` というデータ メンバーが必要です。  
  
> [!NOTE]
>  ATL ダイアログ ウィザードを使用してダイアログ ボックスを作成すると、ウィザードは `enum` の型として自動的に `IDD` のメンバーを追加します。  
  
 `CDialogImpl` は Windows コントロールをホストするモーダルまたはモードレス ダイアログ ボックスを実装できるようにします。  `CAxDialogImpl` は、ActiveX コントロールと Windows 両方のコントロールをホストするモーダルまたはモードレス ダイアログ ボックスを実装できるようにします。  
  
 モーダル ダイアログ ボックスを作成するには、の `CDialogImpl`のインスタンスを派生 \(または派生 `CAxDialogImpl`\-\) を作成します。クラスは、[DoModal](../Topic/CDialogImpl::DoModal.md) のメソッドを呼び出して、  モーダル ダイアログ ボックスを閉じるには、メッセージ ハンドラーから [EndDialog](../Topic/CDialogImpl::EndDialog.md) のメソッドを呼び出します。  モードレス ダイアログ ボックスを作成するには、`DoModal`の代わりに [&#91;作成&#93;](../Topic/CDialogImpl::Create.md) のメソッドを呼び出します。  モードレス ダイアログ ボックスを破棄するには、[DestroyWindow](../Topic/CDialogImpl::DestroyWindow.md)を呼び出します。  
  
 イベントをシンクすることは [CAxDialogImpl](../Topic/CAxDialogImpl%20Class.md)で自動的に行われます。  派生クラスのハンドラー `CWindowImpl`ように、ダイアログ ボックスのメッセージ ハンドラーを実装します。  メッセージ固有の戻り値がある場合は、`LRESULT`として返します。  `LRESULT` の返された値は、Windows のダイアログ マネージャーに応じて適切な処理のために ATL によって割り当てられます。  詳細については、atlwin.h の [CDialogImplBaseT::DialogProc](../Topic/CDialogImpl::DialogProc.md) については、ソース・コードを参照してください。  
  
## 使用例  
 次のクラスはダイアログ ボックスを実装します:  
  
 [!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/CPP/implementing-a-dialog-box_1.h)]  
  
## 参照  
 [ウィンドウ クラス](../Topic/ATL%20Window%20Classes.md)