---
title: "IQuickActivateImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::IQuickActivateImpl"
  - "ATL::IQuickActivateImpl<T>"
  - "ATL.IQuickActivateImpl"
  - "ATL.IQuickActivateImpl<T>"
  - "IQuickActivateImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アクティブ (ATL コントロールを)"
  - "コントロール [ATL], アクティブ"
  - "IQuickActivate ATL の実装"
  - "IQuickActivateImpl クラス"
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IQuickActivateImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、コンテナーのコントロールの初期化を結合して 1 つの呼び出しにします。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<   
class T   
>  
class ATL_NO_VTABLE IQuickActivateImpl :  
public IQuickActivate  
```  
  
#### パラメーター  
 `T`  
 `IQuickActivateImpl`から派生したクラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IQuickActivateImpl::GetContentExtent](../Topic/IQuickActivateImpl::GetContentExtent.md)|実行中のコントロールの現在の表示サイズを取得します。|  
|[IQuickActivateImpl::QuickActivate](../Topic/IQuickActivateImpl::QuickActivate.md)|読み込まれたコントロールの高速な初期化を実行します。|  
|[IQuickActivateImpl::SetContentExtent](../Topic/IQuickActivateImpl::SetContentExtent.md)|どの程度表示領域をコンテナーでコントロールにを割り当てたまたはコントロールに通知します。|  
  
## 解説  
 [IQuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms690146) のインターフェイスのヘルプのコンテナーは、単一の呼び出しの初期化を結合して遅延読み込み時にコントロールを回避できます。  `QuickActivate` のメソッドは、コンテナーがすべてのインターフェイスへのポインターを保持 [QACONTAINER](http://msdn.microsoft.com/library/windows/desktop/ms688630) コントロール自体の構造体へのポインターを渡すようにします。  制御が返されるときに、コントロールがコンテナーによって使用される、独自のインターフェイスへのポインターを保持します [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) の構造体へのポインターを渡します。  クラス `IQuickActivateImpl` は **IQuickActivate** の既定の実装を提供し、デバッグ ビルドでダンプ デバイスに情報を送信して **IUnknown** を実装します。  
  
 **関連トピック** [ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)、[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## 継承階層  
 `IQuickActivate`  
  
 `IQuickActivateImpl`  
  
## 必要条件  
 **Header:** atlctl.h  
  
## 参照  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)