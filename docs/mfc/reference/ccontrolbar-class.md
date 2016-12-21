---
title: "CControlBar クラス | Microsoft Docs"
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
  - "CControlBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CControlBar クラス"
  - "コントロール バー [C++], 基本クラス"
  - "ダイアログ バー, 基本クラス"
  - "OLE サイズ変更バー"
  - "OLE サイズ変更バー, 基本クラス"
  - "ステータス バー, 基本クラス"
  - "ツール バー [C++], 基本クラス"
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
caps.latest.revision: 22
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CControlBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コントロール バー クラスである [CStatusBar](../../mfc/reference/cstatusbar-class.md)、[CToolBar](../../mfc/reference/ctoolbar-class.md)、[CDialogBar](../../mfc/reference/cdialogbar-class.md)、[CReBar](../../mfc/reference/crebar-class.md)、および [COleResizeBar](../../mfc/reference/coleresizebar-class.md) の基底クラスです。  
  
## 構文  
  
```  
class CControlBar : public CWnd  
```  
  
## メンバー  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CControlBar::CControlBar](../Topic/CControlBar::CControlBar.md)|`CControlBar` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CControlBar::CalcDynamicLayout](../Topic/CControlBar::CalcDynamicLayout.md)|[CSize](../../atl-mfc-shared/reference/csize-class.md) オブジェクトとして、ダイナミック コントロール バーのサイズを返します。|  
|[CControlBar::CalcFixedLayout](../Topic/CControlBar::CalcFixedLayout.md)|[CSize](../../atl-mfc-shared/reference/csize-class.md) オブジェクトとして、コントロール バーのサイズを返します。|  
|[CControlBar::CalcInsideRect](../Topic/CControlBar::CalcInsideRect.md)|境界線を含むコントロール バー領域の現在のディメンションを返します。|  
|[CControlBar::DoPaint](../Topic/CControlBar::DoPaint.md)|コントロール バーの境界線およびグリップをレンダリングします。|  
|[CControlBar::DrawBorders](../Topic/CControlBar::DrawBorders.md)|コントロール バーの境界線をレンダリングします。|  
|[CControlBar::DrawGripper](../Topic/CControlBar::DrawGripper.md)|コントロール バーのグリップをレンダリングします。|  
|[CControlBar::EnableDocking](../Topic/CControlBar::EnableDocking.md)|コントロール バーをドッキングまたはフローティングできるようにします。|  
|[CControlBar::GetBarStyle](../Topic/CControlBar::GetBarStyle.md)|コントロール バーのスタイル設定を取得します。|  
|[CControlBar::GetBorders](../Topic/CControlBar::GetBorders.md)|コントロール バーの境界線の値を取得します。|  
|[CControlBar::GetCount](../Topic/CControlBar::GetCount.md)|コントロール バーの `HWND` 以外の要素数を返します。|  
|[CControlBar::GetDockingFrame](../Topic/CControlBar::GetDockingFrame.md)|コントロール バーがドッキングされるフレームへのポインターを返します。|  
|[CControlBar::IsFloating](../Topic/CControlBar::IsFloating.md)|対象のコントロール バーがフローティング コントロール バーである場合に、ゼロ以外の値を返します。|  
|[CControlBar::OnUpdateCmdUI](../Topic/CControlBar::OnUpdateCmdUI.md)|コマンド UI ハンドラーを呼び出します。|  
|[CControlBar::SetBarStyle](../Topic/CControlBar::SetBarStyle.md)|コントロール バーのスタイル設定を変更します。|  
|[CControlBar::SetBorders](../Topic/CControlBar::SetBorders.md)|コントロール バーの境界線の値を設定します。|  
|[CControlBar::SetInPlaceOwner](../Topic/CControlBar::SetInPlaceOwner.md)|コントロール バーのインプレース所有者を変更します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CControlBar::m\_bAutoDelete](../Topic/CControlBar::m_bAutoDelete.md)|ゼロ以外の場合は、Windows のコントロール バーが破棄されると、`CControlBar` オブジェクトが削除されます。|  
|[CControlBar::m\_pInPlaceOwner](../Topic/CControlBar::m_pInPlaceOwner.md)|コントロール バーのインプレース所有者です。|  
  
## 解説  
 通常、コントロール バーは、フレーム ウィンドウの左側または右側にアラインされるウィンドウです。  これには、`HWND` ベースのコントロール \(Windows メッセージを生成し、メッセージに応答するウィンドウ\) または `HWND` ベース以外の項目 \(ウィンドウではなく、アプリケーション コードまたはフレームワーク コードにより管理される項目\) のいずれかである子項目が含まれている場合があります。  `HWND` ベースのコントロールの例としては、リスト ボックスやエディット コントロールがあり、`HWND` ベース以外のコントロールの例としては、ステータス バー ペインやビットマップ ボタンがあります。  
  
 通常、コントロール バーのウィンドウは親フレーム ウィンドウの子ウィンドウであり、通常はクライアント ビューまたはフレーム ウィンドウの MDI クライアントの兄弟です。  `CControlBar` オブジェクトは、親ウィンドウのクライアント領域の四角形に関する情報を使用して、それ自体を配置します。  次に、親ウィンドウのクライアント領域においてどの程度の未割り当て領域が残っているかについて、親ウィンドウに通知します。  
  
 `CControlBar` の詳細については、次を参照してください。  
  
-   [コントロール バー](../Topic/Control%20Bars.md)  
  
-   [テクニカル ノート 31: コントロール バー](../../mfc/tn031-control-bars.md)  
  
-   サポート技術情報の文書 Q242577「PRB: Update Command UI Handlers Do Not Work for Menu Attached to a Dialog Box」  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CControlBar`  
  
## 必要条件  
 **ヘッダー:** afxext.h  
  
## 参照  
 [MFC サンプル CTRLBARS](../../top/visual-cpp-samples.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CToolBar クラス](../../mfc/reference/ctoolbar-class.md)   
 [CDialogBar クラス](../../mfc/reference/cdialogbar-class.md)   
 [CStatusBar クラス](../../mfc/reference/cstatusbar-class.md)   
 [CReBar クラス](../../mfc/reference/crebar-class.md)