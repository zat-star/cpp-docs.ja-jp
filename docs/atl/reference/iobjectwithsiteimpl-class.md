---
title: "IObjectWithSiteImpl クラス | Microsoft Docs"
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
  - "ATL::IObjectWithSiteImpl"
  - "ATL.IObjectWithSiteImpl<T>"
  - "IObjectWithSiteImpl"
  - "ATL.IObjectWithSiteImpl"
  - "ATL::IObjectWithSiteImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IObjectWithSiteImpl クラス"
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IObjectWithSiteImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、オブジェクトとそのサイトとの情報のやり取りを可能にするメソッドが用意されています。  
  
## 構文  
  
```  
  
      template<  
   class T   
>  
class ATL_NO_VTABLE IObjectWithSiteImpl :  
   public IObjectWithSite  
```  
  
#### パラメーター  
 `T`  
 `IObjectWithSiteImpl`から派生したクラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IObjectWithSiteImpl::GetSite](../Topic/IObjectWithSiteImpl::GetSite.md)|インターフェイス ポインターのサイトを照会します。|  
|[IObjectWithSiteImpl::SetChildSite](../Topic/IObjectWithSiteImpl::SetChildSite.md)|サイトの **IUnknown** のポインターをオブジェクトに提供します。|  
|[IObjectWithSiteImpl::SetSite](../Topic/IObjectWithSiteImpl::SetSite.md)|サイトの **IUnknown** のポインターをオブジェクトに提供します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[IObjectWithSiteImpl::m\_spUnkSite](../Topic/IObjectWithSiteImpl::m_spUnkSite.md)|サイトの **IUnknown** のポインターを管理します。|  
  
## 解説  
 [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) のインターフェイスは、オブジェクトがサイトと通信できるようになります。  クラス `IObjectWithSiteImpl` は、このインターフェイスの既定の実装を提供し、デバッグ ビルドでダンプ デバイスに情報を送信して **IUnknown** を実装します。  
  
 `IObjectWithSiteImpl` は 2 とおりの方法を指定します。  サイトの **IUnknown** のポインターを渡すクライアントの最初の呼び出し `SetSite`。  このポインターはオブジェクトに格納されて、`GetSite`の呼び出しにより後で取得できます。  
  
 通常、コントロールではないオブジェクトを作成すると、`IObjectWithSiteImpl` からクラスを取得します。  コントロールに、サイトのポインターを提供する [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)からクラスを派生します。  `IObjectWithSiteImpl` と `IOleObjectImpl`両方からクラスを派生せずにします。  
  
## 継承階層  
 `IObjectWithSite`  
  
 `IObjectWithSiteImpl`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)