---
title: "CStatusBar クラス | Microsoft Docs"
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
  - "CStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBar クラス"
  - "インジケーター"
  - "インジケーター, ステータス バー"
  - "ステータス バー"
  - "ステータス インジケーター"
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStatusBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

テキスト出力用のペインまたは "インジケーター" の行を持つコントロール バーです。  
  
## 構文  
  
```  
class CStatusBar : public CControlBar  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CStatusBar::CStatusBar](../Topic/CStatusBar::CStatusBar.md)|`CStatusBar` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CStatusBar::CommandToIndex](../Topic/CStatusBar::CommandToIndex.md)|特定のインジケーター ID のインデックスを取得します|  
|[CStatusBar::Create](../Topic/CStatusBar::Create.md)|ステータス バーを作成し、`CStatusBar` のオブジェクトにアタッチし、最初のフォントおよびバーの高さを設定します。|  
|[CStatusBar::CreateEx](../Topic/CStatusBar::CreateEx.md)|`CStatusBarCtrl` の埋め込みオブジェクトの追加スタイルの `CStatusBar` のオブジェクトを作成します。|  
|[CStatusBar::DrawItem](../Topic/CStatusBar::DrawItem.md)|オーナー描画のステータス バー コントロールの外観を変更するときに呼び出されます。|  
|[CStatusBar::GetItemID](../Topic/CStatusBar::GetItemID.md)|特定のインデックスのインジケーターの ID を取得します。|  
|[CStatusBar::GetItemRect](../Topic/CStatusBar::GetItemRect.md)|特定のインデックスを表示する四角形を取得します。|  
|[CStatusBar::GetPaneInfo](../Topic/CStatusBar::GetPaneInfo.md)|特定のインデックスのインジケーターの ID、スタイル、および幅を取得します。|  
|[CStatusBar::GetPaneStyle](../Topic/CStatusBar::GetPaneStyle.md)|特定のインデックスのインジケーターのスタイルを取得します。|  
|[CStatusBar::GetPaneText](../Topic/CStatusBar::GetPaneText.md)|特定のインデックスのインジケーターのテキストを取得します。|  
|[CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md)|基になるコモン コントロールであるに直接アクセスできます。|  
|[CStatusBar::SetIndicators](../Topic/CStatusBar::SetIndicators.md)|インジケーターの ID を設定します。|  
|[CStatusBar::SetPaneInfo](../Topic/CStatusBar::SetPaneInfo.md)|特定のインデックスのインジケーターの ID、スタイル、および幅を設定します。|  
|[CStatusBar::SetPaneStyle](../Topic/CStatusBar::SetPaneStyle.md)|特定のインデックスのインジケーターのスタイルを設定します。|  
|[CStatusBar::SetPaneText](../Topic/CStatusBar::SetPaneText.md)|特定のインデックスのインジケーターのテキストを設定します。|  
  
## 解説  
 出力ウィンドウにメッセージ行に自動で表示灯として一般的に使用されます。  例では、ScrollLock キーに、NumLock キーやそのほかのキーの状態を示すインジケーター、および選択されたメニュー コマンドを説明するメニューのヘルプ メッセージの行が含まれます。  
  
 [CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md)の MFC 4.0 に新しいメンバー関数は、ステータス バーのカスタマイズと追加の機能の Windows コモン コントロールのサポートを利用できるようにします。  `CStatusBar` のメンバー関数は、Windows コモン コントロールの機能の最もいます; ただし、`GetStatusBarCtrl`を呼び出すと、Windows 95 \/98 のステータス バー、ステータス バーにの特性をさらに指定できます。  `GetStatusBarCtrl`を呼び出すと、`CStatusBarCtrl` のオブジェクトへの参照を返します。  Windows コモン コントロールを使用してツール バーのデザインに関する詳細については、[CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) を参照してください。  コモン コントロールについては、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [\[コモン コントロール\]](http://msdn.microsoft.com/library/windows/desktop/bb775493) を参照してください。  
  
 フレームワークは、位置 0 に左端のインジケーターを含む配列でインジケーターの情報を格納します。  ステータス バーを作成すると、フレームワークは対応するインジケーターに関連付ける文字列 ID の配列を使用します。  その後、文字列の ID またはインジケーターにアクセスするには、インデックスを使用できます。  
  
 既定では、最初のインジケーターは「ゴム」: そのほかのウィンドウが右寄せで表示されるように、他のインジケーターのウィンドウで使用されていないステータス バーの長さを占有します。  
  
 ステータス バーを作成するには、次の手順を実行する:  
  
1.  `CStatusBar` オブジェクトを構築します。  
  
2.  ステータス バー ペインを作成し、`CStatusBar` のオブジェクトにアタッチするに [&#91;作成&#93;](../Topic/CStatusBar::Create.md) \(または\) [CreateEx](../Topic/CStatusBar::CreateEx.md)関数を呼び出します。  
  
3.  各インジケーターで文字列の ID を関連付けるに [SetIndicators](../Topic/CStatusBar::SetIndicators.md) を呼び出します。  
  
 ステータス バー ペインのテキストを更新する方法が 3 つあります:  
  
1.  ウィンドウ 0 テキストを更新するのみ使用 [CWnd::SetWindowText](../Topic/CWnd::SetWindowText.md)。  
  
2.  ステータス バーの `ON_UPDATE_COMMAND_UI` のハンドラーでは [CCmdUI::SetText](../Topic/CCmdUI::SetText.md)。  
  
3.  ウィンドウのテキストを更新します [SetPaneText](../Topic/CStatusBar::SetPaneText.md)。  
  
 ステータス バー ペインのスタイルを更新します [SetPaneStyle](../Topic/CStatusBar::SetPaneStyle.md)。  
  
 `CStatusBar`の使用の詳細については、" " [MFC ステータス バーの実装](../../mfc/status-bar-implementation-in-mfc.md) と [テクニカル ノート 31: コントロール バー](../../mfc/tn031-control-bars.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CStatusBar`  
  
## 必要条件  
 **Header:** afxext.h  
  
## 参照  
 [MFC CTRLBARS サンプル](../../top/visual-cpp-samples.md)   
 [MFC DLGCBR32 サンプル](../../top/visual-cpp-samples.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CStatusBarCtrl クラス](../../mfc/reference/cstatusbarctrl-class.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)   
 [CWnd::SetWindowText](../Topic/CWnd::SetWindowText.md)   
 [CStatusBar::SetIndicators](../Topic/CStatusBar::SetIndicators.md)