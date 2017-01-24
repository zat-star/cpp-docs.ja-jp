---
title: "CMFCDropDownToolbarButton クラス | Microsoft Docs"
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
  - "CMFCDropDownToolbarButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDropDownToolbarButton クラス"
  - "OnCancelMode メソッド"
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
caps.latest.revision: 31
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDropDownToolbarButton クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ツール バー ボタンの一種で、クリックされたときは標準ボタンと同じように動作します。  ただし、ユーザーがツール バー ボタンを押したままにすると、ドロップダウン ツール バー \([CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)\) が開かれます。  
  
## 構文  
  
```  
class CMFCDropDownToolbarButton : public CMFCToolBarButton  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../Topic/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton.md)|`CMFCDropDownToolbarButton` オブジェクトを構築します。|  
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCDropDownToolbarButton::CopyFrom](../Topic/CMFCDropDownToolbarButton::CopyFrom.md)|別のツール バー ボタンのプロパティを現在のボタンにコピーします。  \([CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md) をオーバーライドします。\)|  
|`CMFCDropDownToolbarButton::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークによって使用されます。|  
|[CMFCDropDownToolbarButton::DropDownToolbar](../Topic/CMFCDropDownToolbarButton::DropDownToolbar.md)|ドロップダウン ツール バーを開きます。|  
|[CMFCDropDownToolbarButton::ExportToMenuButton](../Topic/CMFCDropDownToolbarButton::ExportToMenuButton.md)|ツール バー ボタンのテキストをメニューにコピーします。  \([CMFCToolBarButton::ExportToMenuButton](../Topic/CMFCToolBarButton::ExportToMenuButton.md) をオーバーライドします。\)|  
|[CMFCDropDownToolbarButton::GetDropDownToolBar](../Topic/CMFCDropDownToolbarButton::GetDropDownToolBar.md)|ボタンに関連付けられたドロップダウン ツール バーを取得します。|  
|`CMFCDropDownToolbarButton::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
|[CMFCDropDownToolbarButton::IsDropDown](../Topic/CMFCDropDownToolbarButton::IsDropDown.md)|ドロップダウン ツール バーが現在開いているかどうかを判断します。|  
|[CMFCDropDownToolbarButton::IsExtraSize](../Topic/CMFCDropDownToolbarButton::IsExtraSize.md)|拡張された境界でボタンを表示できるかどうかを指定します。  \([CMFCToolBarButton::IsExtraSize](../Topic/CMFCToolBarButton::IsExtraSize.md) をオーバーライドします。\)|  
|[CMFCDropDownToolbarButton::OnCalculateSize](../Topic/CMFCDropDownToolbarButton::OnCalculateSize.md)|指定されたデバイス コンテキストとドッキングの状態に応じたボタンのサイズを計算するために、フレームワークによって呼び出されます。  \([CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md) をオーバーライドします。\)|  
|`CMFCDropDownToolbarButton::OnCancelMode`|[WM\_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) メッセージを処理するために、フレームワークによって呼び出されます。  \(`CMCToolBarButton::OnCancelMode` をオーバーライドします。\)|  
|[CMFCDropDownToolbarButton::OnChangeParentWnd](../Topic/CMFCDropDownToolbarButton::OnChangeParentWnd.md)|新しいツール バーにボタンが挿入されたときに、フレームワークによって呼び出されます。  \([CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md) をオーバーライドします\)。|  
|[CMFCDropDownToolbarButton::OnClick](../Topic/CMFCDropDownToolbarButton::OnClick.md)|ユーザーがマウス ボタンをクリックしたときに、フレームワークによって呼び出されます。  \([CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md) をオーバーライドします。\)|  
|[CMFCDropDownToolbarButton::OnClickUp](../Topic/CMFCDropDownToolbarButton::OnClickUp.md)|ユーザーがマウス ボタンを放すと、フレームワークによって呼び出されます。  \([CMFCToolBarButton::OnClickUp](../Topic/CMFCToolBarButton::OnClickUp.md) をオーバーライドします。\)|  
|[CMFCDropDownToolbarButton::OnContextHelp](../Topic/CMFCDropDownToolbarButton::OnContextHelp.md)|親ツール バーが `WM_HELPHITTEST` メッセージを処理するときに、フレームワークによって呼び出されます。  \([CMFCToolBarButton::OnContextHelp](../Topic/CMFCToolBarButton::OnContextHelp.md) をオーバーライドします。\)|  
|[CMFCDropDownToolbarButton::OnCustomizeMenu](../Topic/CMFCDropDownToolbarButton::OnCustomizeMenu.md)|アプリケーションで親ツール バーにショートカット メニューを表示するときに提示されるメニューを変更します。  \([CMFCToolBarButton::OnCustomizeMenu](../Topic/CMFCToolBarButton::OnCustomizeMenu.md) をオーバーライドします。\)|  
|[CMFCDropDownToolbarButton::OnDraw](../Topic/CMFCDropDownToolbarButton::OnDraw.md)|指定されたスタイルとオプションを使用してボタンを描画するために、フレームワークによって呼び出されます。  \([CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md) をオーバーライドします。\)|  
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](../Topic/CMFCDropDownToolbarButton::OnDrawOnCustomizeList.md)|**\[カスタマイズ\]** ダイアログ ボックスの **\[コマンド\]** ペインにボタンを描画するために、フレームワークによって呼び出されます。  \([CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md) をオーバーライドします。\)|  
|[CMFCDropDownToolbarButton::Serialize](../Topic/CMFCDropDownToolbarButton::Serialize.md)|このオブジェクトをアーカイブから読み取るか、アーカイブに書き込みます   \([CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md) をオーバーライドします。\)|  
|[CMFCDropDownToolbarButton::SetDefaultCommand](../Topic/CMFCDropDownToolbarButton::SetDefaultCommand.md)|ユーザーがボタンをクリックしたときにフレームワークが使用する既定のコマンドを設定します。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCDropDownToolbarButton::m\_uiShowBarDelay](../Topic/CMFCDropDownToolbarButton::m_uiShowBarDelay.md)|ドロップダウン ツール バーが表示されるまでユーザーがマウス ボタンを押し続ける必要がある時間の長さを指定します。|  
  
## 解説  
 `CMFCDropDownToolBarButton` は標準的なボタンとは異なり、ボタンの右下隅に小さい矢印があります。  ユーザーがドロップダウン ツール バーでボタンを選択すると、そのアイコンがトップレベル ツール バー ボタン \(右下隅に小さい矢印があるボタン\) に表示されます。  
  
 ドロップダウン ツール バーを実装する方法の詳細については、「[CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)」を参照してください。  
  
 `CMFCDropDownToolBarButton` オブジェクトは、[CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md) オブジェクトとしてエクスポートし、ポップアップ メニュー付きのメニュー ボタンとして表示できます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)  
  
## 必要条件  
 **ヘッダー :** afxdropdowntoolbar.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)