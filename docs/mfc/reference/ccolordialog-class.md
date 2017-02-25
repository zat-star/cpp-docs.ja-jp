---
title: "CColorDialog クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CColorDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CColorDialog クラス"
  - "色, ダイアログ ボックス"
  - "ダイアログ ボックス, 色"
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CColorDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

色の選択ダイアログ ボックスをアプリケーションに組み込むことができます。  
  
## 構文  
  
```  
class CColorDialog : public CCommonDialog  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CColorDialog::CColorDialog](../Topic/CColorDialog::CColorDialog.md)|`CColorDialog` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CColorDialog::DoModal](../Topic/CColorDialog::DoModal.md)|色のダイアログ ボックスを表示し、フォントを選択できるようにします。|  
|[CColorDialog::GetColor](../Topic/CColorDialog::GetColor.md)|選択した色の値を含む **COLORREF** の構造体を返します。|  
|[CColorDialog::GetSavedCustomColors](../Topic/CColorDialog::GetSavedCustomColors.md)|ユーザーが作成したカスタム カラーを取得します。|  
|[CColorDialog::SetCurrentColor](../Topic/CColorDialog::SetCurrentColor.md)|指定した色に現在の色の選択を強制します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CColorDialog::OnColorOK](../Topic/CColorDialog::OnColorOK.md)|ダイアログ ボックスに入力された色を検証するためにオーバーライドします。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CColorDialog::m\_cc](../Topic/CColorDialog::m_cc.md)|ダイアログ ボックスの設定をカスタマイズするために使用される構造体。|  
  
## 解説  
 `CColorDialog` オブジェクトは、ディスプレイ システムに対して定義された一連の色を一覧表示するダイアログ ボックスです。  この一覧で特定の色を選択および作成できます。その後ダイアログ ボックスを閉じると、この色がアプリケーションに通知されます。  
  
 `CColorDialog` オブジェクトを構築するには、用意されているコンストラクターを使用するか、新しいクラスを派生させて独自のコンストラクターを使用します。  
  
 ダイアログ ボックスが構築されたら、[m\_cc](../Topic/CColorDialog::m_cc.md) 構造体の任意の値を設定または変更して、ダイアログ ボックスのコントロールの値を初期化できます。  `m_cc` 構造体の型は、[CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830) です。  
  
 ダイアログ ボックスのコントロールを初期化したら、ダイアログ ボックスを表示してユーザーが色を選択できるように、`DoModal` メンバー関数を呼び出します。  `DoModal` は、ユーザーがダイアログ ボックスの \[OK\] \(**IDOK**\) ボタンと \[キャンセル\] \(**IDCANCEL**\) ボタンのどちらをクリックしたかを返します。  
  
 `DoModal` 関数が **IDOK** を返した場合は、入力された情報を取得するために `CColorDialog` メンバー関数の 1 つを使用できます。  
  
 Windows の [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) 関数を使用すると、ダイアログ ボックスの初期化中にエラーが発生したかどうかを確認し、そのエラーについての情報を取得できます。  
  
 `CColorDialog` は、Windows Versions 3.1 以降で配布される COMMDLG.DLL ファイルを使います。  
  
 ダイアログ ボックスをカスタマイズするには、`CColorDialog` からクラスを派生し、独自のダイアログ テンプレートを作成します。さらに、外部のコントロールからの通知メッセージを処理するためにメッセージ マップを追加します。  処理されないメッセージは基本クラスに渡されます。  
  
 フック関数のカスタマイズは必要ありません。  
  
> [!NOTE]
>  フレームワークを使って、他の `CDialog` オブジェクトを淡色表示すると、インストールしたときに `CColorDialog` オブジェクトの背景色が淡色にならないことがあります。  
  
 `CColorDialog`の使い方の詳細については、「[コモン ダイアログ クラス](../../mfc/common-dialog-classes.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 `CColorDialog`  
  
## 必要条件  
 **ヘッダー:** afxdlgs.h  
  
## 参照  
 [MFC MDI サンプル](../../top/visual-cpp-samples.md)   
 [MFC の DRAWCLI サンプル](../../top/visual-cpp-samples.md)   
 [CCommonDialog クラス](../Topic/CCommonDialog%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)