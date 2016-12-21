---
title: "CReBarCtrl クラス | Microsoft Docs"
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
  - "CReBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReBarCtrl クラス"
  - "rebar コントロール, コントロール バー"
  - "rebar コントロール, CReBarCtrl クラス"
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
caps.latest.revision: 23
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CReBarCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rebar コントロールの機能がカプセル化されています。Rebar コントロールは、子ウィンドウを含むコンテナーです。  
  
## 構文  
  
```  
class CReBarCtrl : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CReBarCtrl::CReBarCtrl](../Topic/CReBarCtrl::CReBarCtrl.md)|`CReBarCtrl` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CReBarCtrl::BeginDrag](../Topic/CReBarCtrl::BeginDrag.md)|ドラッグ アンド ドロップ モードに Rebar コントロールを設定します。|  
|[CReBarCtrl::Create](../Topic/CReBarCtrl::Create.md)|Rebar コントロールを作成し、`CReBarCtrl` オブジェクトに結び付けます。|  
|[CReBarCtrl::CreateEx](../Topic/CReBarCtrl::CreateEx.md)|指定されたウィンドウの拡張スタイルの Rebar コントロールを作成し、`CReBarCtrl` のオブジェクトにアタッチします。|  
|[CReBarCtrl::DeleteBand](../Topic/CReBarCtrl::DeleteBand.md)|Rebar コントロールからのバンドを削除します。|  
|[CReBarCtrl::DragMove](../Topic/CReBarCtrl::DragMove.md)|`BeginDrag`の呼び出し後に Rebar コントロールでドラッグする位置を更新します。|  
|[CReBarCtrl::EndDrag](../Topic/CReBarCtrl::EndDrag.md)|Rebar コントロールでドラッグ アンド ドロップ操作を終了します。|  
|[CReBarCtrl::GetBandBorders](../Topic/CReBarCtrl::GetBandBorders.md)|バンドの境界線を取得します。|  
|[CReBarCtrl::GetBandCount](../Topic/CReBarCtrl::GetBandCount.md)|Rebar バンド コントロールの現在の数を取得します。|  
|[CReBarCtrl::GetBandInfo](../Topic/CReBarCtrl::GetBandInfo.md)|Rebar バンド コントロールの指定に関する情報を取得します。|  
|[CReBarCtrl::GetBandMargins](../Topic/CReBarCtrl::GetBandMargins.md)|バンドのマージンを取得します。|  
|[CReBarCtrl::GetBarHeight](../Topic/CReBarCtrl::GetBarHeight.md)|Rebar コントロールの高さを取得します。|  
|[CReBarCtrl::GetBarInfo](../Topic/CReBarCtrl::GetBarInfo.md)|使用するイメージ リストや rebar コントロールについての情報を取得します。|  
|[CReBarCtrl::GetBkColor](../Topic/CReBarCtrl::GetBkColor.md)|Rebar コントロールの既定の背景色を取得します。|  
|[CReBarCtrl::GetColorScheme](../Topic/CReBarCtrl::GetColorScheme.md)|Rebar コントロールに関連付けられている [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) の構造体を取得します。|  
|[CReBarCtrl::GetDropTarget](../Topic/CReBarCtrl::GetDropTarget.md)|rebar コントロールの `IDropTarget` のインターフェイス ポインターを取得します。|  
|[CReBarCtrl::GetExtendedStyle](../Topic/CReBarCtrl::GetExtendedStyle.md)|現在の Rebar コントロールの拡張スタイルを取得します。|  
|[CReBarCtrl::GetImageList](../Topic/CReBarCtrl::GetImageList.md)|Rebar コントロールに関連付けられたイメージ リストを取得します。|  
|[CReBarCtrl::GetPalette](../Topic/CReBarCtrl::GetPalette.md)|Rebar コントロールの現在のパレットを取得します。|  
|[CReBarCtrl::GetRect](../Topic/CReBarCtrl::GetRect.md)|Rebar コントロールの特定のバンドの外接する四角形を取得します。|  
|[CReBarCtrl::GetRowCount](../Topic/CReBarCtrl::GetRowCount.md)|Rebar コントロールのバンドの行の数を取得します。|  
|[CReBarCtrl::GetRowHeight](../Topic/CReBarCtrl::GetRowHeight.md)|rebar コントロールの指定した行の高さを取得します。|  
|[CReBarCtrl::GetTextColor](../Topic/CReBarCtrl::GetTextColor.md)|Rebar コントロールの既定のテキストの色を取得します。|  
|[CReBarCtrl::GetToolTips](../Topic/CReBarCtrl::GetToolTips.md)|Rebar コントロールに関連付けられているすべてのツール ヒント コントロールのハンドルを取得します。|  
|[CReBarCtrl::HitTest](../Topic/CReBarCtrl::HitTest.md)|Rebar バンドがの場合に存在する場合の Rebar バンドのどの部分を画面上の指定された位置にあるかを指定します。|  
|[CReBarCtrl::IDToIndex](../Topic/CReBarCtrl::IDToIndex.md)|Rebar コントロールのバンドのインデックスにバンド \(ID\) の識別子を変換します。|  
|[CReBarCtrl::InsertBand](../Topic/CReBarCtrl::InsertBand.md)|Rebar バンド コントロールの新しいを挿入します。|  
|[CReBarCtrl::MaximizeBand](../Topic/CReBarCtrl::MaximizeBand.md)|最大サイズに rebar コントロールのバンドのサイズを変更します。|  
|[CReBarCtrl::MinimizeBand](../Topic/CReBarCtrl::MinimizeBand.md)|ミニに rebar コントロールのバンドのサイズを変更します。|  
|[CReBarCtrl::MoveBand](../Topic/CReBarCtrl::MoveBand.md)|1 種類のインデックスから別の要素にバンドを実行します。|  
|[CReBarCtrl::PushChevron](../Topic/CReBarCtrl::PushChevron.md)|プログラムにシェブロンを押します。|  
|[CReBarCtrl::RestoreBand](../Topic/CReBarCtrl::RestoreBand.md)|最適なサイズに rebar コントロールのバンドのサイズを変更します。|  
|[CReBarCtrl::SetBandInfo](../Topic/CReBarCtrl::SetBandInfo.md)|rebar コントロールの既存のバンドの特性を設定します。|  
|[CReBarCtrl::SetBandWidth](../Topic/CReBarCtrl::SetBandWidth.md)|現在の Rebar コントロールのドッキング指定されたバンドの幅を設定します。|  
|[CReBarCtrl::SetBarInfo](../Topic/CReBarCtrl::SetBarInfo.md)|rebar コントロールのプロパティを設定します。|  
|[CReBarCtrl::SetBkColor](../Topic/CReBarCtrl::SetBkColor.md)|Rebar コントロールの既定の背景色を設定します。|  
|[CReBarCtrl::SetColorScheme](../Topic/CReBarCtrl::SetColorScheme.md)|Rebar コントロールのボタンの配色を設定します。|  
|[CReBarCtrl::SetExtendedStyle](../Topic/CReBarCtrl::SetExtendedStyle.md)|現在の Rebar コントロールの拡張スタイルを設定します。|  
|[CReBarCtrl::SetImageList](../Topic/CReBarCtrl::SetImageList.md)|rebar コントロールのイメージ リストを設定します。|  
|[CReBarCtrl::SetOwner](../Topic/CReBarCtrl::SetOwner.md)|Rebar コントロールのオーナー ウィンドウを設定します。|  
|[CReBarCtrl::SetPalette](../Topic/CReBarCtrl::SetPalette.md)|Rebar コントロールの現在のパレットを設定します。|  
|[CReBarCtrl::SetTextColor](../Topic/CReBarCtrl::SetTextColor.md)|rebar コントロールの既定のテキストの色を設定します。|  
|[CReBarCtrl::SetToolTips](../Topic/CReBarCtrl::SetToolTips.md)|Rebar コントロールでツール ヒント コントロールに関連付けます。|  
|[CReBarCtrl::SetWindowTheme](../Topic/CReBarCtrl::SetWindowTheme.md)|Rebar コントロールでの視覚スタイルを設定します。|  
|[CReBarCtrl::ShowBand](../Topic/CReBarCtrl::ShowBand.md)|表示と非 rebar コントロールの特定のバンド。|  
|[CReBarCtrl::SizeToRect](../Topic/CReBarCtrl::SizeToRect.md)|指定された四角形に Rebar コントロールにします。|  
  
## 解説  
 Rebar コントロールが常駐するアプリケーションでは、Rebar コントロール内の子ウィンドウが Rebar バンドに割り当てられます。  子ウィンドウは、通常、別のコモン コントロールです。  
  
 Rebar コントロールは 1 つ以上のバンドで構成されます。  それぞれのバンドには、グリップ バー、ビットマップ、テキスト ラベル、子ウィンドウを組み合わせて含めることが可能です。  それぞれの項目は、1 つだけ指定できます。  
  
 Rebar コントロールでは、指定した背景ビットマップに子ウィンドウを表示できます。  **RBBS\_FIXEDSIZE** スタイルを設定しない場合は、Rebar コントロールのすべてのバンドのサイズを変更できます。  バンドの位置またはサイズを変更すると、そのバンドに割り当てられている子ウィンドウのサイズと位置が、Rebar コントロールによって処理されます。  コントロール内のバンドのサイズまたは順序を変更するには、バンドのグリップ バーをクリックしてドラッグします。  
  
 次の図は、3 つのバンド構成の Rebar コントロールです。  
  
-   バンド 0 には、フラットで透明なツール バー コントロールが含まれています。  
  
-   バンド 1 には、透明な標準ボタンと透明なドロップダウン ボタンが含まれています。  
  
-   バンド 2 には、コンボ ボックスと 4 つの標準ボタン含まれています。  
  
     ![Rebar メニューの例](../../mfc/reference/media/vc4scc1.png "vc4SCC1")  
  
## Rebar コントロール  
 Rebar コントロールは以下の機能をサポートします。  
  
-   イメージ リスト。  
  
-   メッセージ処理。  
  
-   カスタム描画機能。  
  
-   標準のウィンドウ スタイルと各種のコントロール スタイル。  スタイルの一覧については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] の「[Rebar Control Styles](http://msdn.microsoft.com/library/windows/desktop/bb774377)」を参照してください。  
  
 詳細については、「[CReBarCtrl の使い方](../Topic/Using%20CReBarCtrl.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CReBarCtrl`  
  
## 必要条件  
 **ヘッダー :** afxcmn.h  
  
## 参照  
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)