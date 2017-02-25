---
title: "COleControlContainer クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleControlContainer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX コントロール コンテナー [C++], コントロール サイト"
  - "COleControlContainer クラス"
  - "カスタム コントロール [MFC], サイト"
ms.assetid: f7ce9246-0fb7-4f07-a83a-6c2390d0fdf8
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# COleControlContainer クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ActiveX コントロールのコントロール コンテナーとして機能します。  
  
## 構文  
  
```  
class COleControlContainer : public CCmdTarget  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleControlContainer::COleControlContainer](../Topic/COleControlContainer::COleControlContainer.md)|`COleControlContainer` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleControlContainer::AttachControlSite](../Topic/COleControlContainer::AttachControlSite.md)|コンテナーによってホストされるコントロール サイトを作成します。|  
|[COleControlContainer::BroadcastAmbientPropertyChange](../Topic/COleControlContainer::BroadcastAmbientPropertyChange.md)|アンビエント プロパティが変更したすべてのホストされているコントロールに通知します。|  
|[COleControlContainer::CheckDlgButton](../Topic/COleControlContainer::CheckDlgButton.md)|指定したボタン コントロールを変更します。|  
|[COleControlContainer::CheckRadioButton](../Topic/COleControlContainer::CheckRadioButton.md)|グループ内の指定したラジオ ボタンを選択します。|  
|[COleControlContainer::CreateControl](../Topic/COleControlContainer::CreateControl.md)|ホストされた ActiveX コントロールを作成します。|  
|[COleControlContainer::CreateOleFont](../Topic/COleControlContainer::CreateOleFont.md)|OLE フォントを作成します。|  
|[COleControlContainer::FindItem](../Topic/COleControlContainer::FindItem.md)|指定されたコントロールのカスタム サイトを返します。|  
|[COleControlContainer::FreezeAllEvents](../Topic/COleControlContainer::FreezeAllEvents.md)|コントロール サイトがイベントを使用するかどうかを判定します。|  
|[COleControlContainer::GetAmbientProp](../Topic/COleControlContainer::GetAmbientProp.md)|指定されたアンビエント プロパティを取得します。|  
|[COleControlContainer::GetDlgItem](../Topic/COleControlContainer::GetDlgItem.md)|指定されたダイアログのコントロールを取得します。|  
|[COleControlContainer::GetDlgItemInt](../Topic/COleControlContainer::GetDlgItemInt.md)|指定されたダイアログのコントロールの値を取得します。|  
|[COleControlContainer::GetDlgItemText](../Topic/COleControlContainer::GetDlgItemText.md)|指定されたダイアログのコントロールのキャプションを取得します。|  
|[COleControlContainer::HandleSetFocus](../Topic/COleControlContainer::HandleSetFocus.md)|コンテナーが `WM_SETFOCUS` のメッセージを処理するかどうかを判定します。|  
|[COleControlContainer::HandleWindowlessMessage](../Topic/COleControlContainer::HandleWindowlessMessage.md)|ウィンドウなしのコントロールに送信されるメッセージを処理します。|  
|[COleControlContainer::IsDlgButtonChecked](../Topic/COleControlContainer::IsDlgButtonChecked.md)|指定したボタンの状態が決まります。|  
|[COleControlContainer::OnPaint](../Topic/COleControlContainer::OnPaint.md)|コンテナーの一部を再描画するために呼び出されます。|  
|[COleControlContainer::OnUIActivate](../Topic/COleControlContainer::OnUIActivate.md)|コントロールがアクティブになった埋め込み先であるとすると呼び出されます。|  
|[COleControlContainer::OnUIDeactivate](../Topic/COleControlContainer::OnUIDeactivate.md)|コントロールが非アクティブになるときに呼び出されます。|  
|[COleControlContainer::ScrollChildren](../Topic/COleControlContainer::ScrollChildren.md)|スクロール メッセージが子ウィンドウから受け取ったときに、フレームワークによって呼び出されます。|  
|[COleControlContainer::SendDlgItemMessage](../Topic/COleControlContainer::SendDlgItemMessage.md)|指定されたコントロールにメッセージを送ります。|  
|[COleControlContainer::SetDlgItemInt](../Topic/COleControlContainer::SetDlgItemInt.md)|指定されたコントロールの値を設定します。|  
|[COleControlContainer::SetDlgItemText](../Topic/COleControlContainer::SetDlgItemText.md)|指定されたコントロールのテキストを設定します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[COleControlContainer::m\_crBack](../Topic/COleControlContainer::m_crBack.md)|コンテナーの背景色。|  
|[COleControlContainer::m\_crFore](../Topic/COleControlContainer::m_crFore.md)|コンテナーの前景色。|  
|[COleControlContainer::m\_listSitesOrWnds](../Topic/COleControlContainer::m_listSitesOrWnds.md)|サポートされるコントロール サイトのリスト。|  
|[COleControlContainer::m\_nWindowlessControls](../Topic/COleControlContainer::m_nWindowlessControls.md)|ホストされるウィンドウなしのコントロールの数。|  
|[COleControlContainer::m\_pOleFont](../Topic/COleControlContainer::m_pOleFont.md)|カスタム コントロール サイトの OLE フォントへのポインター。|  
|[COleControlContainer::m\_pSiteCapture](../Topic/COleControlContainer::m_pSiteCapture.md)|キャプチャのコントロールへのポインター。|  
|[COleControlContainer::m\_pSiteFocus](../Topic/COleControlContainer::m_pSiteFocus.md)|現在入力フォーカスを持つコントロールへのポインター。|  
|[COleControlContainer::m\_pSiteUIActive](../Topic/COleControlContainer::m_pSiteUIActive.md)|現在アクティブな埋め込み先であるコントロールへのポインター。|  
|[COleControlContainer::m\_pWnd](../Topic/COleControlContainer::m_pWnd.md)|コントロール コンテナーを実装するウィンドウへのポインター。|  
|[COleControlContainer::m\_siteMap](../Topic/COleControlContainer::m_siteMap.md)|サイト マップ。|  
  
## 解説  
 これは、一つ以上の ActiveX コントロール サイトがサポートされます \( `COleControlSite`で実行されます\) を提供する。  `COleControlContainer` は完全に [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770) と [IOleContainer](http://msdn.microsoft.com/library/windows/desktop/ms690103) のインターフェイスを実装して、埋め込み先アイテムとして資格を達成するために含まれている ActiveX コントロールができます。  
  
 一般に、`COccManager` と `COleControlSite` とともにこのクラスが一つ以上の ActiveX コントロールのカスタム サイトを使用してカスタム ActiveX コントロール コンテナーを実装するために使用されます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `COleControlContainer`  
  
## 必要条件  
 **ヘッダー :** afxocc.h  
  
## 参照  
 [CCmdTarget クラス](../Topic/CCmdTarget%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleControlSite クラス](../../mfc/reference/colecontrolsite-class.md)   
 [COccManager クラス](../../mfc/reference/coccmanager-class.md)