---
title: "CComPolyObject クラス | Microsoft Docs"
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
  - "CComPolyObject"
  - "ATL.CComPolyObject<contained>"
  - "ATL::CComPolyObject"
  - "ATL::CComPolyObject<contained>"
  - "ATL.CComPolyObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "集約オブジェクト [C++], ATL で"
  - "集約 [C++], ATL オブジェクト"
  - "CComPolyObject クラス"
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComPolyObject クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、集約オブジェクトまたは非集約オブジェクトの **IUnknown** を実装します。  
  
## 構文  
  
```  
  
      template<  
   class contained   
>  
class CComPolyObject : public IUnknown, public CComObjectRootEx  
   < contained::_ThreadModel::ThreadModelNoCS >  
```  
  
#### パラメーター  
 `contained`  
 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) か [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)から、または他のインターフェイスからクラスが派生したオブジェクトでサポートする必要があります。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComPolyObject::CComPolyObject](../Topic/CComPolyObject::CComPolyObject.md)|コンストラクターです。|  
|[CComPolyObject::~CComPolyObject](../Topic/CComPolyObject::~CComPolyObject.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComPolyObject::AddRef](../Topic/CComPolyObject::AddRef.md)|オブジェクトの参照カウントをインクリメントします。|  
|[CComPolyObject::CreateInstance](../Topic/CComPolyObject::CreateInstance.md)|\(静的関数\) [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)のオーバーヘッドを避けて **CComPolyObject\<** 新しい`contained`**\>** のオブジェクトを作成することもできます。|  
|[CComPolyObject::FinalConstruct](../Topic/CComPolyObject::FinalConstruct.md)|`m_contained`の最終的な初期化を実行します。|  
|[CComPolyObject::FinalRelease](../Topic/CComPolyObject::FinalRelease.md)|`m_contained`の最後の破棄を実行します。|  
|[CComPolyObject::QueryInterface](../Topic/CComPolyObject::QueryInterface.md)|要求されたインターフェイスへのポインターを取得します。|  
|[CComPolyObject::Release](../Topic/CComPolyObject::Release.md)|オブジェクトの参照カウントをデクリメントします。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CComPolyObject::m\_contained](../Topic/CComPolyObject::m_contained.md)|オブジェクトが集約するオブジェクトを集約した場合、またはオブジェクトの **IUnknown** にデリゲート **IUnknown** の外側への呼び出しを認識できません。|  
  
## 解説  
 集約オブジェクトまたは非集約オブジェクトのを実装します`CComPolyObject`[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)。  
  
 `CComPolyObject` のインスタンスが作成されると、外側の不明の値がチェックされます。  これは **null**場合、**IUnknown** は集約オブジェクトに実装されます。  外側の **null**が不明である、**IUnknown** は集約オブジェクトに実装されます。  
  
 `CComPolyObject` を使用する利点は集約されます。集約ケースを処理するモジュールで [CComAggObject](../../atl/reference/ccomaggobject-class.md) と [CComObject](../../atl/reference/ccomobject-class.md) の両方があることを避けるためです。  `CComPolyObject` の単一のオブジェクトは両方を処理します。  これは、vtable の 1 種類のコピーと関数の 1 のコピーは、モジュールであることを意味します。  、vtable の場合、これは大幅に、モジュールのサイズを抑えることができます。  ただし、ようになります `CComAggObject` と `CComObject`がやや多くのモジュールのサイズで vtable が小さく、集約または非集約オブジェクト用に最適化されていないため `CComPolyObject` を使用して行われます。  
  
 `DECLARE_POLY_AGGREGATABLE` のマクロがオブジェクトのクラス定義で指定されている場合、オブジェクトを作成するために、`CComPolyObject` が使用されます。  `DECLARE_POLY_AGGREGATABLE` が自動的にフル コントロール、Internet Explorer コントロールの作成に ATL プロジェクト ウィザードを使用して宣言されます。  
  
 集計すると、`CComPolyObject` のオブジェクトに、外部オブジェクトの **IUnknown**とは別に、独自の **IUnknown**が独自の参照カウントを保持します。  `CComPolyObject` は、外側の不明に代行させるために [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) を使用します。  
  
 集計に関する詳細については、" " [ATL COM オブジェクトの基本](../../atl/fundamentals-of-atl-com-objects.md)を参照してください。  
  
## 継承階層  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComPolyObject`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md)   
 [クラスの概要](../../atl/atl-class-overview.md)