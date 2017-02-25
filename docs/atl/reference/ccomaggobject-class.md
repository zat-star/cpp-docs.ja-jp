---
title: "CComAggObject クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComAggObject<contained>"
  - "ATL.CComAggObject"
  - "ATL.CComAggObject<contained>"
  - "CComAggObject"
  - "ATL::CComAggObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "集約オブジェクト [C++], ATL で"
  - "集約 [C++], ATL オブジェクト"
  - "CComAggObject クラス"
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CComAggObject クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、集約オブジェクトの [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) のインターフェイスを実装します。  定義上、集約オブジェクトは、外部オブジェクト内に格納されます。  `CComAggObject` のクラスは [CComObject クラス](../../atl/reference/ccomobject-class.md)に似ていますが、外部クライアントに直接アクセスできるインターフェイスを公開します。  
  
## 構文  
  
```  
  
      template<  
   class contained  
>  
class CComAggObject :  
   public IUnknown, public CComObjectRootEx  
   < contained::_ThreadModel::ThreadModelNoCS >  
```  
  
#### パラメーター  
 `contained`  
 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) か [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)から、または他のインターフェイスからクラスが派生したオブジェクトでサポートする必要があります。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComAggObject::CComAggObject](../Topic/CComAggObject::CComAggObject.md)|コンストラクターです。|  
|[CComAggObject::~CComAggObject](../Topic/CComAggObject::~CComAggObject.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComAggObject::AddRef](../Topic/CComAggObject::AddRef.md)|集約オブジェクトの参照カウントをインクリメントします。|  
|[CComAggObject::CreateInstance](../Topic/CComAggObject::CreateInstance.md)|この静的関数は [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)のオーバーヘッドを避けて **CComAggObject\<** 新しい`contained`**\>** のオブジェクトを作成できるようにします。|  
|[CComAggObject::FinalConstruct](../Topic/CComAggObject::FinalConstruct.md)|`m_contained`の最終的な初期化を実行します。|  
|[CComAggObject::FinalRelease](../Topic/CComAggObject::FinalRelease.md)|`m_contained`の最後の破棄を実行します。|  
|[CComAggObject::QueryInterface](../Topic/CComAggObject::QueryInterface.md)|要求されたインターフェイスへのポインターを取得します。|  
|[CComAggObject::Release](../Topic/CComAggObject::Release.md)|集約オブジェクトの参照カウントをデクリメントします。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CComAggObject::m\_contained](../Topic/CComAggObject::m_contained.md)|外側の不明にデリゲートの呼び出し `IUnknown`。|  
  
## 解説  
 集約オブジェクトの`CComAggObject` の 実装 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)。  `CComAggObject` に、外部オブジェクトの **IUnknown** のインターフェイスとは別に、**IUnknown** の独自のインターフェイスが独自の参照カウントを保持します。  
  
 集計に関する詳細については、" " [ATL COM オブジェクトの基本](../../atl/fundamentals-of-atl-com-objects.md)を参照してください。  
  
## 継承階層  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComAggObject`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [CComObject クラス](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md)   
 [DECLARE\_ONLY\_AGGREGATABLE](../Topic/DECLARE_ONLY_AGGREGATABLE.md)   
 [DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)   
 [クラスの概要](../../atl/atl-class-overview.md)