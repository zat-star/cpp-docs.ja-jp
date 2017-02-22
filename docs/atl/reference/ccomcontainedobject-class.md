---
title: "CComContainedObject クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComContainedObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "集約オブジェクト [C++], ATL で"
  - "集約 [C++], ATL オブジェクト"
  - "CComContainedObject クラス"
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CComContainedObject クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、オーナー オブジェクトの **IUnknown** に処理を任せることによって、[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) を実装します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
class Base   
>  
class CComContainedObject :  
public Base  
```  
  
#### パラメーター  
 `Base`  
 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) か [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)から派生したクラス。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComContainedObject::CComContainedObject](../Topic/CComContainedObject::CComContainedObject.md)|コンストラクターです。  オーナー オブジェクトのメンバーに `IUnknown`のポインターを初期化します。|  
|[CComContainedObject::~CComContainedObject](../Topic/CComContainedObject::~CComContainedObject.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComContainedObject::AddRef](../Topic/CComContainedObject::AddRef.md)|オーナー オブジェクトの参照カウントをインクリメントします。|  
|[CComContainedObject::GetControllingUnknown](../Topic/CComContainedObject::GetControllingUnknown.md)|オーナー オブジェクトの `IUnknown`を取得します。|  
|[CComContainedObject::QueryInterface](../Topic/CComContainedObject::QueryInterface.md)|オーナー オブジェクトで必要なインターフェイスへのポインターを取得します。|  
|[CComContainedObject::Release](../Topic/CComContainedObject::Release.md)|オーナー オブジェクトの参照カウントをデクリメントします。|  
  
## 解説  
 ATL は、クラス [CComAggObject](../../atl/reference/ccomaggobject-class.md)、[CComPolyObject](../../atl/reference/ccompolyobject-class.md)と [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)で `CComContainedObject` を使用します。  `CComContainedObject` は、オーナー オブジェクトの **IUnknown**へのデリゲートによって [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) を実装します。  \(所有者は集計の外部オブジェクトが、オブジェクトが作成されるティアオフ インターフェイス\)。`CComContainedObject` は完全に `Base`によって継承される `CComObjectRootEx` の `OuterQueryInterface`、`OuterAddRef`と `OuterRelease`を呼び出します。  
  
## 継承階層  
 `Base`  
  
 `CComContainedObject`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)