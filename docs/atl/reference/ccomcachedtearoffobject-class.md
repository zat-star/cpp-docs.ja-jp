---
title: "CComCachedTearOffObject クラス | Microsoft Docs"
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
  - "ATL::CComCachedTearOffObject"
  - "ATL.CComCachedTearOffObject"
  - "ATL.CComCachedTearOffObject<contained>"
  - "CComCachedTearOffObject"
  - "ATL::CComCachedTearOffObject<contained>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "キャッシュ, ATL のキャッシュされたティアオフ オブジェクト"
  - "CComCachedTearOffObject クラス"
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComCachedTearOffObject クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、ティアオフ インターフェイスの [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) を実装します。  
  
## 構文  
  
```  
  
      template <  
   class contained  
>  
class CComCachedTearOffObject : public IUnknown,  
   public CComObjectRootEx< contained::_ThreadModel::ThreadModelNoCS >  
```  
  
#### パラメーター  
 `contained`  
 `CComTearOffObjectBase` から派生したクラスのティアオフ インターフェイス、およびサポートへのティアオフのオブジェクトを関連付けます。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComCachedTearOffObject::CComCachedTearOffObject](../Topic/CComCachedTearOffObject::CComCachedTearOffObject.md)|コンストラクターです。|  
|[CComCachedTearOffObject::~CComCachedTearOffObject](../Topic/CComCachedTearOffObject::~CComCachedTearOffObject.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComCachedTearOffObject::AddRef](../Topic/CComCachedTearOffObject::AddRef.md)|`CComCachedTearOffObject` のオブジェクトの参照カウントをインクリメントします。|  
|[CComCachedTearOffObject::FinalConstruct](../Topic/CComCachedTearOffObject::FinalConstruct.md)|`m_contained::FinalConstruct` \(ティアオフ クラスのメソッド\) を呼び出します。|  
|[CComCachedTearOffObject::FinalRelease](../Topic/CComCachedTearOffObject::FinalRelease.md)|`m_contained::FinalRelease` \(ティアオフ クラスのメソッド\) を呼び出します。|  
|[CComCachedTearOffObject::QueryInterface](../Topic/CComCachedTearOffObject::QueryInterface.md)|`CComCachedTearOffObject` のオブジェクトの `IUnknown` は、のティアオフ クラス \(クラス\) `contained`の要求されたインターフェイスへのポインターを返します。|  
|[CComCachedTearOffObject::Release](../Topic/CComCachedTearOffObject::Release.md)|参照カウントが 0 の場合 `CComCachedTearOffObject` のオブジェクトの参照カウントをデクリメントし、破棄します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CComCachedTearOffObject::m\_contained](../Topic/CComCachedTearOffObject::m_contained.md)|アプリケーションのティアオフ `contained`クラス \(クラス\) から派生 `CComContainedObject` のオブジェクト。|  
  
## 解説  
 ティアオフ インターフェイスの`CComCachedTearOffObject` の 実装 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)。  このクラスは `CComTearOffObject` とオーナー オブジェクトの **IUnknown** とは別に `CComCachedTearOffObject` に独自の **IUnknown**があることとは異なります \(所有者は、ティアオフが作成されているオブジェクトです。  `CComCachedTearOffObject` は、参照カウントがゼロの場合 **IUnknown** の独自の参照カウントを保持し、削除します。  ただし、ティアオフ インターフェイスに対してもただせば、オーナー オブジェクトの **IUnknown** の参照カウントがインクリメントします。  
  
 ティアオフを実装する `CComCachedTearOffObject` のオブジェクトが既にインスタンス化され、ティアオフ インターフェイスが再びにただされれば、`CComCachedTearOffObject` の同じオブジェクトが再利用されます。  これに対し `CComTearOffObject` によって実装されるティアオフ インターフェイスがオーナー オブジェクトを経由するには、もう一度ただされれば、別の `CComTearOffObject` がインスタンス化されます。  
  
 所有者クラスは `FinalRelease` を実装し、参照カウントをデクリメントします `CComCachedTearOffObject`のキャッシュされた **IUnknown** の **\[リリース\]** を呼び出す必要があります。  これにより `CComCachedTearOffObject` の `FinalRelease` が呼び出され、ティアオフを削除します。  
  
## 継承階層  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComCachedTearOffObject`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [CComTearOffObject クラス](../../atl/reference/ccomtearoffobject-class.md)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)