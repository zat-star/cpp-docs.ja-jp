---
title: "IOleInPlaceActiveObjectImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IOleInPlaceActiveObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX コントロール [C++], 通信 (コンテナーとコントロール間の)"
  - "IOleInPlaceActiveObject, ATL の実装"
  - "IOleInPlaceActiveObjectImpl クラス"
ms.assetid: 44e6cc6d-a2dc-4187-98e3-73cf0320dea9
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# IOleInPlaceActiveObjectImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、埋め込み先コントロールとそのコンテナーとの情報のやり取りを支援するメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template< class   
      T  
      >  
class IOleInPlaceActiveObjectImpl  
```  
  
#### パラメーター  
 `T`  
 `IOleInPlaceActiveObjectImpl`から派生したクラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IOleInPlaceActiveObjectImpl::ContextSensitiveHelp](../Topic/IOleInPlaceActiveObjectImpl::ContextSensitiveHelp.md)|状況依存のヘルプを有効にします。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IOleInPlaceActiveObjectImpl::EnableModeless](../Topic/IOleInPlaceActiveObjectImpl::EnableModeless.md)|モードレス ダイアログ ボックスを有効にします。  ATL 実装は、`S_OK`を返します。|  
|[IOleInPlaceActiveObjectImpl::GetWindow](../Topic/IOleInPlaceActiveObjectImpl::GetWindow.md)|ウィンドウ ハンドルを取得します。|  
|[IOleInPlaceActiveObjectImpl::OnDocWindowActivate](../Topic/IOleInPlaceActiveObjectImpl::OnDocWindowActivate.md)|コンテナーのドキュメント ウィンドウがアクティブまたは非アクティブ化されたときにコントロールに通知します。  ATL 実装は、`S_OK`を返します。|  
|[IOleInPlaceActiveObjectImpl::OnFrameWindowActivate](../Topic/IOleInPlaceActiveObjectImpl::OnFrameWindowActivate.md)|コンテナーのトップレベルのフレーム ウィンドウがアクティブまたは非アクティブ化されたときにコントロールに通知します。  ATL 実装を返します|  
|[IOleInPlaceActiveObjectImpl::ResizeBorder](../Topic/IOleInPlaceActiveObjectImpl::ResizeBorder.md)|境界線のサイズを変更する必要があるコントロールに通知します。  ATL 実装は、`S_OK`を返します。|  
|[IOleInPlaceActiveObjectImpl::TranslateAccelerator](../Topic/IOleInPlaceActiveObjectImpl::TranslateAccelerator.md)|コンテナーからメニューのアクセラレータ キーのメッセージを処理します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
  
## 解説  
 [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299) のインターフェイスは、埋め込み先コントロールとそのコンテナーとの通信を行う; たとえば、コントロールとコンテナーのアクティブ状態を伝達、およびコントロールを通知する場合は、独自のサイズを変更する必要があります。  クラス `IOleInPlaceActiveObjectImpl` は `IOleInPlaceActiveObject` の既定の実装を提供し、デバッグ ビルドでダンプ デバイスに情報を送信して **IUnknown** をサポートします。  
  
 **関連トピック** [ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)、[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## 継承階層  
 `IOleInPlaceActiveObject`  
  
 `IOleInPlaceActiveObjectImpl`  
  
## 必要条件  
 **Header:** atlctl.h  
  
## 参照  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX Controls Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [クラスの概要](../../atl/atl-class-overview.md)