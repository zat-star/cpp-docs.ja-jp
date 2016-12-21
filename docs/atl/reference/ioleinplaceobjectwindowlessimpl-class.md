---
title: "IOleInPlaceObjectWindowlessImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IOleInPlaceObjectWindowlessImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アクティベーション [C++], ATL"
  - "ActiveX コントロール [C++], 通信 (コンテナーとコントロール間の)"
  - "コントロール [ATL], ウィンドウなしの"
  - "非アクティブ (ATL を)"
  - "IOleInPlaceObjectWindowless, ATL の実装"
  - "IOleInPlaceObjectWindowlessImpl クラス"
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IOleInPlaceObjectWindowlessImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは **IUnknown** を実装します。また、ウィンドウなしのコントロールでもウィンドウ メッセージの受け取りやドラッグ アンド ドロップ処理を可能にするメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template< class   
      T  
      >  
class IOleInPlaceObjectWindowlessImpl  
```  
  
#### パラメーター  
 `T`  
 `IOleInPlaceObjectWindowlessImpl`から派生したクラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](../Topic/IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp.md)|状況依存のヘルプを有効にします。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](../Topic/IOleInPlaceObjectWindowlessImpl::GetDropTarget.md)|サポートがドラッグ アンド ドロップできます。埋め込み先でアクティブ、ウィンドウなしのオブジェクトの `IDropTarget` のインターフェイスを提供します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IOleInPlaceObjectWindowlessImpl::GetWindow](../Topic/IOleInPlaceObjectWindowlessImpl::GetWindow.md)|ウィンドウ ハンドルを取得します。|  
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](../Topic/IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate.md)|アクティブな埋め込み先コントロールを非アクティブ化します。|  
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](../Topic/IOleInPlaceObjectWindowlessImpl::OnWindowMessage.md)|コンテナーから埋め込み先編集が有効なウィンドウなしのコントロールにメッセージをディスパッチします。|  
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](../Topic/IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo.md)|前に非アクティブにコントロールを再アクティブ化します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](../Topic/IOleInPlaceObjectWindowlessImpl::SetObjectRects.md)|埋め込み先のコントロールのどの部分が表示されるかを示します。|  
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](../Topic/IOleInPlaceObjectWindowlessImpl::UIDeactivate.md)|非アクティブ化、削除は、ユーザー インターフェイス、埋め込み先編集の有効化をサポートします。|  
  
## 解説  
 [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) のインターフェイスは、埋め込み先のコントロールの再アクティブ化と非アクティブ化を管理し、表示するかコントロールの量を判断します。  [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) のインターフェイスは、ウィンドウ メッセージを受信し、ドラッグ アンド ドロップ操作への参加をウィンドウなしのコントロールができます。  クラス `IOleInPlaceObjectWindowlessImpl` は `IOleInPlaceObject` と `IOleInPlaceObjectWindowless` の既定の実装を提供し、デバッグ ビルドでダンプ デバイスに情報を送信して **IUnknown** を実装します。  
  
 **関連トピック** [ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)、[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## 継承階層  
 `IOleInPlaceObjectWindowless`  
  
 `IOleInPlaceObjectWindowlessImpl`  
  
## 必要条件  
 **Header:** atlctl.h  
  
## 参照  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)