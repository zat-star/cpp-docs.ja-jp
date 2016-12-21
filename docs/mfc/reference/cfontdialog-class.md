---
title: "CFontDialog クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFontDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFontDialog クラス"
  - "ダイアログ ボックス, フォント"
  - "フォント"
  - "フォント, 選択"
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
caps.latest.revision: 25
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFontDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

フォントの選択ダイアログ ボックスをアプリケーションに組み込むことができます。  
  
## 構文  
  
```  
class CFontDialog : public CCommonDialog  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CFontDialog::CFontDialog](../Topic/CFontDialog::CFontDialog.md)|`CFontDialog` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CFontDialog::DoModal](../Topic/CFontDialog::DoModal.md)|ダイアログ ボックスを表示し、フォントを選択できるようにします。|  
|[CFontDialog::GetCharFormat](../Topic/CFontDialog::GetCharFormat.md)|選択したフォントの文字書式を取得します。|  
|[CFontDialog::GetColor](../Topic/CFontDialog::GetColor.md)|選択されているフォントの色を返します。|  
|[CFontDialog::GetCurrentFont](../Topic/CFontDialog::GetCurrentFont.md)|`LOGFONT` 構造体に現在選択されているフォントの特性を割り当てます。|  
|[CFontDialog::GetFaceName](../Topic/CFontDialog::GetFaceName.md)|選択されているフォントの書体名を返します。|  
|[CFontDialog::GetSize](../Topic/CFontDialog::GetSize.md)|選択されているフォントのポイント サイズを返します。|  
|[CFontDialog::GetStyleName](../Topic/CFontDialog::GetStyleName.md)|選択されているフォントのスタイル名を返します。|  
|[CFontDialog::GetWeight](../Topic/CFontDialog::GetWeight.md)|選択されているフォントの太さを返します。|  
|[CFontDialog::IsBold](../Topic/CFontDialog::IsBold.md)|フォントが太字かどうかを調べます。|  
|[CFontDialog::IsItalic](../Topic/CFontDialog::IsItalic.md)|フォントが斜体かどうかを調べます。|  
|[CFontDialog::IsStrikeOut](../Topic/CFontDialog::IsStrikeOut.md)|フォントが取り消し線付きかどうかを調べます。|  
|[CFontDialog::IsUnderline](../Topic/CFontDialog::IsUnderline.md)|フォントが下線付きかどうかを調べます。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CFontDialog::m\_cf](../Topic/CFontDialog::m_cf.md)|`CFontDialog` オブジェクトをカスタマイズするために使われる構造体。|  
  
## 解説  
 `CFontDialog` オブジェクトは、現在システムにインストールされているフォントを一覧表示するダイアログ ボックスです。  この一覧から特定のフォントを選択できます。さらに選択結果をアプリケーションに返すことができます。  
  
 `CFontDialog` オブジェクトを構築するには、提供されたコンストラクターを使うか、新しいサブクラスを派生させて、独自のコンストラクターを使います。  
  
 `CFontDialog` オブジェクトを構築すると、`m_cf` 構造体を使ってダイアログ ボックスのコントロールの値やステータスを初期化できます。  [m\_cf](../Topic/CFontDialog::m_cf.md) 構造体は [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832) 型です。  この構造体の詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] を参照してください。  
  
 ダイアログ オブジェクトのコントロールを初期化したら、ダイアログ ボックスを表示してユーザーがフォントを選択できるように、`DoModal` メンバー関数を呼び出します。  `DoModal` は、ユーザーが \[OK\] \(**IDOK**\) ボタンと \[キャンセル\] \(**IDCANCEL**\) ボタンのどちらをクリックしたかを返します。  
  
 `DoModal` 関数が **IDOK** を返した場合は、入力された情報を取得するために `CFontDialog` メンバー関数の 1 つを使用できます。  
  
 Windows の [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) 関数を使用すると、ダイアログ ボックスの初期化中にエラーが発生したかどうかを確認し、そのエラーについての情報を取得できます。  この関数の詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] を参照してください。  
  
 `CFontDialog` は、Windows Versions 3.1 以降で配布される COMMDLG.DLL ファイルを使います。  
  
 ダイアログ ボックスをカスタマイズするには、`CFontDialog` からクラスを派生し、独自のダイアログ テンプレートを作成します。さらに、拡張コントロールからの通知メッセージを処理するためのメッセージ マップを追加します。  処理されないメッセージは基本クラスに渡されます。  
  
 フック関数のカスタマイズは必要ありません。  
  
 `CFontDialog` の使い方の詳細については、「[コモン ダイアログ クラス](../../mfc/common-dialog-classes.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 `CFontDialog`  
  
## 必要条件  
 **ヘッダー:** afxdlgs.h  
  
## 参照  
 [MFC HIERSVR サンプル](../../top/visual-cpp-samples.md)   
 [CCommonDialog クラス](../Topic/CCommonDialog%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)