---
title: "IPointerInactiveImpl クラス | Microsoft Docs"
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
  - "IPointerInactiveImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アクティブでないオブジェクト"
  - "IPointerInactive ATL の実装"
  - "IPointerInactiveImpl クラス"
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IPointerInactiveImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、**IUnknown** および [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712) インターフェイス メソッドを実装します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template< class   
      T  
      >  
class IPointerInactiveImpl  
```  
  
#### パラメーター  
 `T`  
 `IPointerInactiveImpl`から派生したクラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IPointerInactiveImpl::GetActivationPolicy](../Topic/IPointerInactiveImpl::GetActivationPolicy.md)|オブジェクトの現在のアクティブ化ポリシーを取得します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IPointerInactiveImpl::OnInactiveMouseMove](../Topic/IPointerInactiveImpl::OnInactiveMouseMove.md)|マウス ポインターをボタンの上に、オブジェクトがマウス イベントを発生できることを示します実行されたことを通知するにオブジェクト。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IPointerInactiveImpl::OnInactiveSetCursor](../Topic/IPointerInactiveImpl::OnInactiveSetCursor.md)|アクティブなオブジェクトにマウス ポインターを設定します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
  
## 解説  
 アクティブなオブジェクトまたは実行するだけに読み込まれる 1 になります。  アクティブなオブジェクトとは異なり、アクティブなオブジェクトは、Windows のマウスおよびキーボード メッセージを受け取ることができません。  したがって、アクティブなオブジェクトが少ないリソースを使用し、通常は有効です。  
  
 [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712) のインターフェイスがアクティブなときにオブジェクトがマウス操作の最小をサポートするようにします。  この機能はコントロールに特に役立ちます。  
  
 **E\_NOTIMPL**を返すことによって `IPointerInactiveImpl` の実装 `IPointerInactive` のメソッドを使用します。  ただし、デバッグ ビルドでダンプ デバイスに情報を送信して **IUnknown** を実装します。  
  
 **関連トピック** [ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)、[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## 継承階層  
 `IPointerInactive`  
  
 `IPointerInactiveImpl`  
  
## 必要条件  
 **Header:** atlctl.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)