---
title: "IOleObjectImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.IOleObjectImpl"
  - "ATL.IOleObjectImpl<T>"
  - "ATL::IOleObjectImpl"
  - "ATL::IOleObjectImpl<T>"
  - "IOleObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX コントロール [C++], 通信 (コンテナーとコントロール間の)"
  - "IOleObject, ATL の実装"
  - "IOleObjectImpl クラス"
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IOleObjectImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは **IUnknown** を実装します。また、コンテナーがコントロールと情報をやり取りするための基本インターフェイスとなります。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
class T   
>  
class ATL_NO_VTABLE IOleObjectImpl :  
public IOleObject  
```  
  
#### パラメーター  
 `T`  
 `IOleObjectImpl`から派生したクラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IOleObjectImpl::Advise](../Topic/IOleObjectImpl::Advise.md)|コントロールを使用してアドバイザリ コネクションを確立します。|  
|[IOleObjectImpl::Close](../Topic/IOleObjectImpl::Close.md)|から読み込まれるにコントロールの状態を実行する変更します。|  
|[IOleObjectImpl::DoVerb](../Topic/IOleObjectImpl::DoVerb.md)|コントロールを列挙されたアクションの 1 を実行するように指定します。|  
|[IOleObjectImpl::DoVerbDiscardUndo](../Topic/IOleObjectImpl::DoVerbDiscardUndo.md)|コントロールを元に戻す保持している状態を破棄するように指定します。|  
|[IOleObjectImpl::DoVerbHide](../Topic/IOleObjectImpl::DoVerbHide.md)|コントロールをビューからユーザー インターフェイスを削除します。|  
|[IOleObjectImpl::DoVerbInPlaceActivate](../Topic/IOleObjectImpl::DoVerbInPlaceActivate.md)|コントロールをウィンドウの移動およびインストールされませんが、コントロールのユーザー インターフェイスをインストールします。|  
|[IOleObjectImpl::DoVerbOpen](../Topic/IOleObjectImpl::DoVerbOpen.md)|コントロールを別のウィンドウで開きます編集します。|  
|[IOleObjectImpl::DoVerbPrimary](../Topic/IOleObjectImpl::DoVerbPrimary.md)|ユーザーがコントロールをダブルクリックしたときに指定したアクションが実行されます。  コントロールは、通常、埋め込みコントロールを起動するアクションを定義します。|  
|[IOleObjectImpl::DoVerbShow](../Topic/IOleObjectImpl::DoVerbShow.md)|ユーザーに新しく挿入されたコントロールを示しています。|  
|[IOleObjectImpl::DoVerbUIActivate](../Topic/IOleObjectImpl::DoVerbUIActivate.md)|埋め込みコントロールをアクティブにして、メニューやツール バーなどのコントロールのユーザー インターフェイスを示します。|  
|[IOleObjectImpl::EnumAdvise](../Topic/IOleObjectImpl::EnumAdvise.md)|コントロールのアドバイザリ コネクションを列挙します。|  
|[IOleObjectImpl::EnumVerbs](../Topic/IOleObjectImpl::EnumVerbs.md)|コントロールのアクションを列挙します。|  
|[IOleObjectImpl::GetClientSite](../Topic/IOleObjectImpl::GetClientSite.md)|コントロールのクライアント サイトを取得します。|  
|[IOleObjectImpl::GetClipboardData](../Topic/IOleObjectImpl::GetClipboardData.md)|クリップボードからデータを取得します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IOleObjectImpl::GetExtent](../Topic/IOleObjectImpl::GetExtent.md)|コントロールの表示領域の範囲を取得します。|  
|[IOleObjectImpl::GetMiscStatus](../Topic/IOleObjectImpl::GetMiscStatus.md)|コントロールの状態を取得します。|  
|[IOleObjectImpl::GetMoniker](../Topic/IOleObjectImpl::GetMoniker.md)|コントロールのモニカーを取得します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IOleObjectImpl::GetUserClassID](../Topic/IOleObjectImpl::GetUserClassID.md)|コントロールのクラス ID を取得します。|  
|[IOleObjectImpl::GetUserType](../Topic/IOleObjectImpl::GetUserType.md)|コントロールでユーザー入力の名前を取得します。|  
|[IOleObjectImpl::InitFromData](../Topic/IOleObjectImpl::InitFromData.md)|選択したデータからコントロールを初期化します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IOleObjectImpl::IsUpToDate](../Topic/IOleObjectImpl::IsUpToDate.md)|コントロールが最新かどうかを確認します。  ATL 実装は、`S_OK`を返します。|  
|[IOleObjectImpl::OnPostVerbDiscardUndo](../Topic/IOleObjectImpl::OnPostVerbDiscardUndo.md)|元に戻すの状態の後に [DoVerbDiscardUndo](../Topic/IOleObjectImpl::DoVerbDiscardUndo.md) によって呼び出されます。破棄されます。|  
|[IOleObjectImpl::OnPostVerbHide](../Topic/IOleObjectImpl::OnPostVerbHide.md)|コントロールの後に [DoVerbHide](../Topic/IOleObjectImpl::DoVerbHide.md) によって呼び出されます。非表示にされます。|  
|[IOleObjectImpl::OnPostVerbInPlaceActivate](../Topic/IOleObjectImpl::OnPostVerbInPlaceActivate.md)|コントロールの後に [DoVerbInPlaceActivate](../Topic/IOleObjectImpl::DoVerbInPlaceActivate.md) によって呼び出されます。アクティブ化されます。|  
|[IOleObjectImpl::OnPostVerbOpen](../Topic/IOleObjectImpl::OnPostVerbOpen.md)|コントロールを別のペインで編集用に開いた後 [DoVerbOpen](../Topic/IOleObjectImpl::DoVerbOpen.md) が呼び出されます。|  
|[IOleObjectImpl::OnPostVerbShow](../Topic/IOleObjectImpl::OnPostVerbShow.md)|コントロールが表示されるように [DoVerbShow](../Topic/IOleObjectImpl::DoVerbShow.md) された後で呼び出されます。|  
|[IOleObjectImpl::OnPostVerbUIActivate](../Topic/IOleObjectImpl::OnPostVerbUIActivate.md)|コントロールのユーザー インターフェイスがアクティブになった後で [DoVerbUIActivate](../Topic/IOleObjectImpl::DoVerbUIActivate.md) が呼び出されます。|  
|[IOleObjectImpl::OnPreVerbDiscardUndo](../Topic/IOleObjectImpl::OnPreVerbDiscardUndo.md)|元に戻すの状態の前に [DoVerbDiscardUndo](../Topic/IOleObjectImpl::DoVerbDiscardUndo.md) によって呼び出されます。破棄されます。|  
|[IOleObjectImpl::OnPreVerbHide](../Topic/IOleObjectImpl::OnPreVerbHide.md)|コントロールの前に [DoVerbHide](../Topic/IOleObjectImpl::DoVerbHide.md) によって呼び出されます。非表示にされます。|  
|[IOleObjectImpl::OnPreVerbInPlaceActivate](../Topic/IOleObjectImpl::OnPreVerbInPlaceActivate.md)|コントロールの前に [DoVerbInPlaceActivate](../Topic/IOleObjectImpl::DoVerbInPlaceActivate.md) によって呼び出されます。アクティブ化されます。|  
|[IOleObjectImpl::OnPreVerbOpen](../Topic/IOleObjectImpl::OnPreVerbOpen.md)|コントロールを別のペインの編集用に開いた前に [DoVerbOpen](../Topic/IOleObjectImpl::DoVerbOpen.md) が呼び出されます。|  
|[IOleObjectImpl::OnPreVerbShow](../Topic/IOleObjectImpl::OnPreVerbShow.md)|コントロールが表示されるようにする前に [DoVerbShow](../Topic/IOleObjectImpl::DoVerbShow.md) が呼び出されます。|  
|[IOleObjectImpl::OnPreVerbUIActivate](../Topic/IOleObjectImpl::OnPreVerbUIActivate.md)|コントロールのユーザー インターフェイスがアクティブになった前に [DoVerbUIActivate](../Topic/IOleObjectImpl::DoVerbUIActivate.md) が呼び出されます。|  
|[IOleObjectImpl::SetClientSite](../Topic/IOleObjectImpl::SetClientSite.md)|コンテナーのクライアント サイトに関するコントロールを指定します。|  
|[IOleObjectImpl::SetColorScheme](../Topic/IOleObjectImpl::SetColorScheme.md)|コントロール アプリケーションにある場合、配色をお勧めします。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IOleObjectImpl::SetExtent](../Topic/IOleObjectImpl::SetExtent.md)|コントロールの表示領域の範囲を設定します。|  
|[IOleObjectImpl::SetHostNames](../Topic/IOleObjectImpl::SetHostNames.md)|コントロールのコンテナー アプリケーションとドキュメント コンテナーの名前を指定します。|  
|[IOleObjectImpl::SetMoniker](../Topic/IOleObjectImpl::SetMoniker.md)|モニカーを何にコントロールに指示します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IOleObjectImpl::Unadvise](../Topic/IOleObjectImpl::Unadvise.md)|コントロールを使用してアドバイザリ コネクションを削除します。|  
|[IOleObjectImpl::Update](../Topic/IOleObjectImpl::Update.md)|コントロールを更新します。  ATL 実装は、`S_OK`を返します。|  
  
## 解説  
 [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709) のインターフェイスは、コンテナーがコントロールと通信する主なインターフェイスです。  クラス `IOleObjectImpl` は、このインターフェイスの既定の実装を提供し、デバッグ ビルドでダンプ デバイスに情報を送信して **IUnknown** を実装します。  
  
 **関連トピック** [ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)、[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## 継承階層  
 `IOleObject`  
  
 `IOleObjectImpl`  
  
## 必要条件  
 **Header:** atlctl.h  
  
## 参照  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX Controls Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [クラスの概要](../../atl/atl-class-overview.md)