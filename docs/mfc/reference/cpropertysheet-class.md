---
title: "CPropertySheet クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPropertySheet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPropertySheet クラス"
  - "ダイアログ ボックス, タブ"
  - "プロパティ シート, CPropertySheet クラス"
  - "タブ ダイアログ ボックス"
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
caps.latest.revision: 30
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPropertySheet クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

タブ ダイアログ ボックスとしても知られるプロパティ シートを表します。  
  
## 構文  
  
```  
class CPropertySheet : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CPropertySheet::CPropertySheet](../Topic/CPropertySheet::CPropertySheet.md)|`CPropertySheet` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CPropertySheet::AddPage](../Topic/CPropertySheet::AddPage.md)|プロパティ シートにページを追加します。|  
|[CPropertySheet::Construct](../Topic/CPropertySheet::Construct.md)|`CPropertySheet` オブジェクトを構築します。|  
|[CPropertySheet::Create](../Topic/CPropertySheet::Create.md)|モードレス プロパティ シートを表示します。|  
|[CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md)|モーダルのプロパティ シートを表示します。|  
|[CPropertySheet::EnableStackedTabs](../Topic/CPropertySheet::EnableStackedTabs.md)|プロパティ シートが左右に並べて表示またはスクロール タブを使用するかどうかを示します。|  
|[CPropertySheet::EndDialog](../Topic/CPropertySheet::EndDialog.md)|プロパティ シートを終了します。|  
|[CPropertySheet::GetActiveIndex](../Topic/CPropertySheet::GetActiveIndex.md)|プロパティ シートのアクティブなページのインデックスを取得します。|  
|[CPropertySheet::GetActivePage](../Topic/CPropertySheet::GetActivePage.md)|アクティブ ページのオブジェクトを返します。|  
|[CPropertySheet::GetPage](../Topic/CPropertySheet::GetPage.md)|指定したページへのポインターを取得します。|  
|[CPropertySheet::GetPageCount](../Topic/CPropertySheet::GetPageCount.md)|プロパティ シートのページ数を取得します。|  
|[CPropertySheet::GetPageIndex](../Topic/CPropertySheet::GetPageIndex.md)|プロパティ シートの指定したページのインデックスを取得します。|  
|[CPropertySheet::GetTabControl](../Topic/CPropertySheet::GetTabControl.md)|タブ コントロールへのポインターを取得します。|  
|[CPropertySheet::MapDialogRect](../Topic/CPropertySheet::MapDialogRect.md)|四角形のダイアログ ボックス単位を単位を除外するに変換します。|  
|[CPropertySheet::OnInitDialog](../Topic/CPropertySheet::OnInitDialog.md)|プロパティ シートの初期化処理を拡張するためにオーバーライドします。|  
|[CPropertySheet::PressButton](../Topic/CPropertySheet::PressButton.md)|プロパティ シートの指定したボタンのクリックをシミュレートします。|  
|[CPropertySheet::RemovePage](../Topic/CPropertySheet::RemovePage.md)|プロパティ シートからページを削除します。|  
|[CPropertySheet::SetActivePage](../Topic/CPropertySheet::SetActivePage.md)|プログラムでアクティブ ページのオブジェクトを設定します。|  
|[CPropertySheet::SetFinishText](../Topic/CPropertySheet::SetFinishText.md)|完了のボタンのテキストを設定します。|  
|[CPropertySheet::SetTitle](../Topic/CPropertySheet::SetTitle.md)|プロパティ シート キャプションを設定します。|  
|[CPropertySheet::SetWizardButtons](../Topic/CPropertySheet::SetWizardButtons.md)|ウィザードのボタンを有効にします。|  
|[CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md)|ウィザード モードを有効にします。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CPropertySheet::m\_psh](../Topic/CPropertySheet::m_psh.md)|Windows の構造 [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546)。  基本プロパティ シートのパラメーターへのアクセスを提供します。|  
  
## 解説  
 プロパティ シートは、1 つの `CPropertySheet` オブジェクトと、1 つ以上の [CPropertyPage](../../mfc/reference/cpropertypage-class.md) オブジェクトで構成されます。  フレームワークは、一連のタブ インデックスを持ち、現在選択されているページが表示される領域のあるウィンドウとしてプロパティ シートを表示します。  ユーザーは、該当するタブを使用して特定のページに移動します。  
  
 `CPropertySheet` では、[!INCLUDE[Win98](../../mfc/reference/includes/win98_md.md)] および Windows NT 2000 で導入された、拡張 [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) 構造体がサポートされています。  この構造体には、"ウォーターマーク" の背景ビットマップの使用をサポートする追加のフラグとメンバーが含まれます。  
  
 この新しいイメージをプロパティ シート オブジェクトに自動的に表示するには、[CPropertySheet::Construct](../Topic/CPropertySheet::Construct.md) または [CPropertySheet::CPropertySheet](../Topic/CPropertySheet::CPropertySheet.md) を呼び出し、ビットマップ イメージとパレット イメージの有効な値を渡します。  
  
 `CPropertySheet` は [CDialog](../../mfc/reference/cdialog-class.md) から派生されてはいませんが、`CPropertySheet` オブジェクトの管理は、`CDialog` オブジェクトの管理と同じように行われます。  たとえば、プロパティ シートの作成は 2 段階で行われます。まずコンストラクターを呼び出し、次に、モーダル プロパティ シートでは [DoModal](../Topic/CPropertySheet::DoModal.md) を、モードレス プロパティ シートでは [Create](../Topic/CPropertySheet::Create.md) を呼び出します。  `CPropertySheet` には、[CPropertySheet::Construct](../Topic/CPropertySheet::Construct.md) と [CPropertySheet::CPropertySheet](../Topic/CPropertySheet::CPropertySheet.md) の 2 種類のコンストラクターがあります。  
  
 `CPropertySheet` オブジェクトを構築するときに、一部の [ウィンドウ スタイル](../Topic/Window%20Styles.md)によって初回例外が発生する可能性があります。  これは、まだ作成されていないプロパティ シートのスタイルをシステムが変更しようとするために起こります。  この例外を回避するには、独自の `CPropertySheet` を作成するときに次のスタイルを設定してください。  
  
-   DS\_3DLOOK  
  
-   DS\_CONTROL  
  
-   WS\_CHILD  
  
-   WS\_TABSTOP  
  
 次のオプションのスタイルも、初回例外を引き起こすことなく使用できます。  
  
-   DS\_SHELLFONT  
  
-   DS\_LOCALEDIT  
  
-   WS\_CLIPCHILDREN  
  
 これ以外の `Window Styles` は禁止されているので、有効にしないでください。  
  
 `CPropertySheet` オブジェクトと外部オブジェクトの間でのデータの交換は、`CDialog` オブジェクトとのデータ交換に似ています。  大きな違いは、プロパティ シートの設定は、通常、`CPropertySheet` オブジェクト自身のメンバー変数ではなく、`CPropertyPage` オブジェクトのメンバー変数になっているという点です。  
  
 ウィザードと呼ばれる型のタブ ダイアログ ボックスを作成できます。このダイアログ ボックスは、デバイスのセットアップやニュースレターの作成のような、操作の手順をユーザーに示す一連のプロパティ ページを持つプロパティ シートで構成されています。  ウィザード型のタブ ダイアログ ボックスでは、プロパティ ページにタブがなく、一度に 1 つのプロパティ ページだけが表示されます。  また、ウィザード型のタブ ダイアログ ボックスは、**\[OK\]** ボタンや **\[今すぐ適用\]** ボタンの代わりに、**\[戻る\]**、**\[次へ\]**、**\[完了\]**、**\[キャンセル\]**、および **\[ヘルプ\]** の各ボタンを持ちます。  
  
 ウィザード型ダイアログ ボックスを作成する手順は、標準のプロパティ シートの作成手順と同じですが、[DoModal](../Topic/CPropertySheet::DoModal.md) を呼び出す前に、[SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md) を呼び出します。  ウィザード ボタンを有効にするには、その機能や外観をカスタマイズするためのフラグを使って [SetWizardButtons](../Topic/CPropertySheet::SetWizardButtons.md) を呼び出します。  **\[完了\]** ボタンを有効にするには、ウィザードの最後のページでユーザーが操作を行った後に [SetFinishText](../Topic/CPropertySheet::SetFinishText.md) を呼び出します。  
  
 `CPropertySheet` オブジェクトの使い方の詳細については、「[プロパティ シートとプロパティ ページ](../../mfc/property-sheets-and-property-pages-in-mfc.md)」を参照してください。  また、サポート技術情報の「HOWTO: Create a Modeless CPropertySheet with Standard Buttons \(Q146916\)」および「HOWTO: Design a Resizable MFC Property Sheet \(Q300606\)」も参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CPropertySheet`  
  
## 必要条件  
 **ヘッダー :** afxdlgs.h  
  
## 参照  
 [MFC CMNCTRL1 サンプル](../../top/visual-cpp-samples.md)   
 [MFC CMNCTRL2 サンプル](../../top/visual-cpp-samples.md)   
 [MFC PROPDLG サンプル](../../top/visual-cpp-samples.md)   
 [MFC SNAPVW サンプル](../../top/visual-cpp-samples.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)