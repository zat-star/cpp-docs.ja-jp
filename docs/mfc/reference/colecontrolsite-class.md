---
title: "COleControlSite クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleControlSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleControlSite クラス"
ms.assetid: 43970644-5eab-434a-8ba6-56d144ff1e3f
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleControlSite クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

クライアント側のカスタム コントロール インターフェイスをサポートします。  
  
## 構文  
  
```  
class COleControlSite : public CCmdTarget  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleControlSite::COleControlSite](../Topic/COleControlSite::COleControlSite.md)|`COleControlSite` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleControlSite::BindDefaultProperty](../Topic/COleControlSite::BindDefaultProperty.md)|データ ソースにホストされているコントロールの既定のプロパティをバインドします。|  
|[COleControlSite::BindProperty](../Topic/COleControlSite::BindProperty.md)|データ ソースにホストされるコントロールのプロパティをバインドします。|  
|[COleControlSite::CreateControl](../Topic/COleControlSite::CreateControl.md)|ホストされた ActiveX コントロールを作成します。|  
|[COleControlSite::DestroyControl](../Topic/COleControlSite::DestroyControl.md)|ホストされているコントロールを破棄します。|  
|[COleControlSite::DoVerb](../Topic/COleControlSite::DoVerb.md)|ホストされているコントロールの特定の動詞を実装します。|  
|[COleControlSite::EnableDSC](../Topic/COleControlSite::EnableDSC.md)|コントロール サイトのデータの調達を有効にします。|  
|[COleControlSite::EnableWindow](../Topic/COleControlSite::EnableWindow.md)|コントロール サイトを有効にします。|  
|[COleControlSite::FreezeEvents](../Topic/COleControlSite::FreezeEvents.md)|コントロール サイトがイベントを受け取ると指定します。|  
|[COleControlSite::GetDefBtnCode](../Topic/COleControlSite::GetDefBtnCode.md)|ホストされているコントロールの既定のボタン コードを取得します。|  
|[COleControlSite::GetDlgCtrlID](../Topic/COleControlSite::GetDlgCtrlID.md)|コントロールの識別子を取得します。|  
|[COleControlSite::GetEventIID](../Topic/COleControlSite::GetEventIID.md)|ホストされているコントロールのイベントのインターフェイス ID を取得します。|  
|[COleControlSite::GetExStyle](../Topic/COleControlSite::GetExStyle.md)|コントロール サイトの拡張スタイルを取得します。|  
|[COleControlSite::GetProperty](../Topic/COleControlSite::GetProperty.md)|ホストされているコントロールの特定のプロパティを取得します。|  
|[COleControlSite::GetStyle](../Topic/COleControlSite::GetStyle.md)|コントロール サイトのスタイルを取得します。|  
|[COleControlSite::GetWindowText](../Topic/COleControlSite::GetWindowText.md)|ホストされているコントロールのテキストを取得します。|  
|[COleControlSite::InvokeHelper](../Topic/COleControlSite::InvokeHelper.md)|ホストされているコントロールの特定のメソッドを呼び出します。|  
|[COleControlSite::InvokeHelperV](../Topic/COleControlSite::InvokeHelperV.md)|引数リストを指定してホストされるコントロールの特定のメソッドを呼び出します。|  
|[COleControlSite::IsDefaultButton](../Topic/COleControlSite::IsDefaultButton.md)|コントロールがウィンドウの既定のボタンかどうかを判定します。|  
|[COleControlSite::IsWindowEnabled](../Topic/COleControlSite::IsWindowEnabled.md)|コントロール サイトの表示状態をチェックします。|  
|[COleControlSite::ModifyStyle](../Topic/COleControlSite::ModifyStyle.md)|コントロール サイトの現在の拡張スタイルを変更します。|  
|[COleControlSite::ModifyStyleEx](../Topic/COleControlSite::ModifyStyleEx.md)|コントロール サイトの現在のスタイルを変更します。|  
|[COleControlSite::MoveWindow](../Topic/COleControlSite::MoveWindow.md)|コントロール サイトの位置を変更します。|  
|[COleControlSite::QuickActivate](../Topic/COleControlSite::QuickActivate.md)|高速ホストされているコントロールをアクティブにします。|  
|[COleControlSite::SafeSetProperty](../Topic/COleControlSite::SafeSetProperty.md)|例外をスローする可能性を持たないコントロールのプロパティまたはメソッドを設定します。|  
|[COleControlSite::SetDefaultButton](../Topic/COleControlSite::SetDefaultButton.md)|ペインの既定のボタンを設定します。|  
|[COleControlSite::SetDlgCtrlID](../Topic/COleControlSite::SetDlgCtrlID.md)|コントロールの識別子を取得します。|  
|[COleControlSite::SetFocus](../Topic/COleControlSite::SetFocus.md)|コントロール サイトにフォーカスを設定します。|  
|[COleControlSite::SetProperty](../Topic/COleControlSite::SetProperty.md)|ホストされているコントロールの特定のプロパティを設定します。|  
|[COleControlSite::SetPropertyV](../Topic/COleControlSite::SetPropertyV.md)|引数リストを指定してホストされているコントロールの特定のプロパティを設定します。|  
|[COleControlSite::SetWindowPos](../Topic/COleControlSite::SetWindowPos.md)|コントロール サイトの位置を設定します。|  
|[COleControlSite::SetWindowText](../Topic/COleControlSite::SetWindowText.md)|ホストされているコントロールのテキストを設定します。|  
|[COleControlSite::ShowWindow](../Topic/COleControlSite::ShowWindow.md)|表示と非コントロール サイト。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleControlSite::GetControlInfo](../Topic/COleControlSite::GetControlInfo.md)|ホストされているコントロールの取得の情報とキーボード ニーモニック。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[COleControlSite::m\_bIsWindowless](../Topic/COleControlSite::m_bIsWindowless.md)|ホストされるコントロールがウィンドウなしのコントロールであるかどうかを判定します。|  
|[COleControlSite::m\_ctlInfo](../Topic/COleControlSite::m_ctlInfo.md)|コントロールにキーボード処理の情報が含まれます。|  
|[COleControlSite::m\_dwEventSink](../Topic/COleControlSite::m_dwEventSink.md)|コントロールのコネクション ポイントのクッキー。|  
|[COleControlSite::m\_dwMiscStatus](../Topic/COleControlSite::m_dwMiscStatus.md)|ホストされるコントロールのさまざまな状態。|  
|[COleControlSite::m\_dwPropNotifySink](../Topic/COleControlSite::m_dwPropNotifySink.md)|コントロールの `IPropertyNotifySink` クッキー。|  
|[COleControlSite::m\_dwStyle](../Topic/COleControlSite::m_dwStyle.md)|ホストされているコントロールのスタイル。|  
|[COleControlSite::m\_hWnd](../Topic/COleControlSite::m_hWnd.md)|コントロール サイトのハンドル。|  
|[COleControlSite::m\_iidEvents](../Topic/COleControlSite::m_iidEvents.md)|ホストされているコントロールのイベント インターフェイスの ID。|  
|[COleControlSite::m\_nID](../Topic/COleControlSite::m_nID.md)|ホストされているコントロールの ID。|  
|[COleControlSite::m\_pActiveObject](../Topic/COleControlSite::m_pActiveObject.md)|ホストされるコントロールの `IOleInPlaceActiveObject` オブジェクトへのポインター。|  
|[COleControlSite::m\_pCtrlCont](../Topic/COleControlSite::m_pCtrlCont.md)|ホストされているコントロールのコンテナー。|  
|[COleControlSite::m\_pInPlaceObject](../Topic/COleControlSite::m_pInPlaceObject.md)|ホストされるコントロールの `IOleInPlaceObject` オブジェクトへのポインター。|  
|[COleControlSite::m\_pObject](../Topic/COleControlSite::m_pObject.md)|コントロールの `IOleObjectInterface` インターフェイスへのポインター。|  
|[COleControlSite::m\_pWindowlessObject](../Topic/COleControlSite::m_pWindowlessObject.md)|コントロールの `IOleInPlaceObjectWindowless` インターフェイスへのポインター。|  
|[COleControlSite::m\_pWndCtrl](../Topic/COleControlSite::m_pWndCtrl.md)|ホストされているコントロールのウィンドウ オブジェクトへのポインター。|  
|[COleControlSite::m\_rect](../Topic/COleControlSite::m_rect.md)|コントロール サイトの寸法。|  
  
## 解説  
 このサポートは、ActiveX コントロールがその場所に関する情報と表示のサイト、モニカー、ユーザー インターフェイス、アンビエント プロパティとコンテナーに用意されている他のリソースのエクステントを取得する主要な手段です。  `COleControlSite` は完全に [IOleControlSite](http://msdn.microsoft.com/library/windows/desktop/ms688502)、[IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586)、[IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706)、[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)、**IBoundObjectSite**、**INotifyDBEvents**の [IRowSetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) のインターフェイスを実装します。  また、IDispatch インターフェイスは、\(サポートをアンビエント プロパティとイベント シンクに公開されます\) 実行されます。  
  
 `COleControlSite`を使用して ActiveX コントロール サイトを作成するには、`COleControlSite`からクラスを派生します。  \-次の `CWnd`コンテナー \(たとえば、ダイアログ ボックス\) オーバーライドの派生クラス **CWnd::CreateControlSite** 関数。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `COleControlSite`  
  
## 必要条件  
 **ヘッダー :** afxocc.h  
  
## 参照  
 [CCmdTarget クラス](../Topic/CCmdTarget%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleControlContainer クラス](../../mfc/reference/colecontrolcontainer-class.md)