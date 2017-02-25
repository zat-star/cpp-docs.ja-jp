---
title: "CComObjectRootEx クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComObjectRootEx"
  - "ATL::CComObjectRootEx<ThreadModel>"
  - "CComObjectRootEx"
  - "ATL::CComObjectRootEx"
  - "ATL.CComObjectRootEx<ThreadModel>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "参照カウント"
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CComObjectRootEx クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、非集約オブジェクトと集約オブジェクトの両方について、オブジェクトの参照カウントを管理するメソッドが用意されています。  
  
## 構文  
  
```  
  
      template<  
   class ThreadModel   
>  
class CComObjectRootEx : public CComObjectRootBase  
```  
  
#### パラメーター  
 `ThreadModel`  
 メソッドを使用して、目的のスレッド モデルを実装するクラス。  [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)、[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)、または [CComMultiThreadModelNoCS](../Topic/CComMultiThreadModelNoCS%20Class.md)へ `ThreadModel` を設定することによって明示的にスレッド モデルを選択できます。  [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) か [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)へ `ThreadModel` を設定して、サーバーの既定のスレッド モデルを使用できます。  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[CComObjectRootEx](../Topic/CComObjectRootEx::CComObjectRootEx.md)|コンストラクターです。|  
|[InternalAddRef](../Topic/CComObjectRootEx::InternalAddRef.md)|集約オブジェクトの参照カウントをインクリメントします。|  
|[InternalRelease](../Topic/CComObjectRootEx::InternalRelease.md)|集約オブジェクトの参照カウントをデクリメントします。|  
|[ロック](../Topic/CComObjectRootEx::Lock.md)|スレッド モデルはマルチスレッドの場合、クリティカル セクション オブジェクトの所有権を取得します。|  
|[&#91;ロック解除&#93;](../Topic/CComObjectRootEx::Unlock.md)|スレッド モデルはマルチスレッドの場合、クリティカル セクション オブジェクトの所有権を解放します。|  
  
### CComObjectRootBase のメソッド  
  
|||  
|-|-|  
|[FinalConstruct](../Topic/CComObjectRootEx::FinalConstruct.md)|独自のオブジェクトに必要な初期化を実行するクラスでをオーバーライドします。|  
|[FinalRelease](../Topic/CComObjectRootEx::FinalRelease.md)|独自のオブジェクトに必要なクリーンアップを実行するクラスでをオーバーライドします。|  
|[OuterAddRef](../Topic/CComObjectRootEx::OuterAddRef.md)|集約オブジェクトの参照カウントをインクリメントします。|  
|[OuterQueryInterface](../Topic/CComObjectRootEx::OuterQueryInterface.md)|集約オブジェクトの外側で **IUnknown** へのデリゲート。|  
|[OuterRelease](../Topic/CComObjectRootEx::OuterRelease.md)|集約オブジェクトの参照カウントをデクリメントします。|  
  
### 静的関数  
  
|||  
|-|-|  
|[InternalQueryInterface](../Topic/CComObjectRootEx::InternalQueryInterface.md)|集約オブジェクトの **IUnknown** へのデリゲート。|  
|[ObjectMain](../Topic/CComObjectRootEx::ObjectMain.md)|派生クラスのモジュールの初期化と終了時に呼び出されます。オブジェクト マップに示します。|  
  
### データ メンバー  
  
|||  
|-|-|  
|[m\_dwRef](../Topic/CComObjectRootEx::m_dwRef.md)|`m_pOuterUnknown`では、共用体の部分。  `AddRef` と **\[リリース\]**の参照カウントを保持するオブジェクトが集約されない場合に使用されます。|  
|[m\_pOuterUnknown](../Topic/CComObjectRootEx::m_pOuterUnknown.md)|`m_dwRef`では、共用体の部分。  外側の演算子へのポインターを保持するオブジェクトが集約されたときに使用します。|  
  
## 解説  
 非集約オブジェクトの`CComObjectRootEx` ハンドルのオブジェクトの参照カウントを管理します。  これは、のオブジェクトを集約する場合は、オブジェクトを集約する保持し、外側の不明にポインターを保持するオブジェクトの参照カウントを示します。  集約オブジェクトに対して構成要素へのオブジェクトの内部エラーの処理に、`CComObjectRootEx` のメソッドが使用でき、内側のインターフェイスが解放される内部オブジェクトまたは保護するために削除された場合、削除の外部オブジェクトが。  
  
 COM サーバーを実装するクラスは `CComObjectRootEx` か [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)から継承する必要があります。  
  
 は、をクラス定義が [DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md) のマクロを指定すると、ATL は **IClassFactory::CreateInstance** が呼び出されたときに **CComPolyObjectCYourClass** のインスタンスを作成します。  作成時に、外側の不明の値がチェックされます。  これは **null**場合、**IUnknown** は集約オブジェクトに実装されます。  外側の **null**が不明である、**IUnknown** は集約オブジェクトに実装されます。  
  
 は、クラスが `DECLARE_POLY_AGGREGATABLE` のマクロを指定する、ATL は集約オブジェクトの **CAggComObjectCYourClass** のインスタンスや非集約オブジェクトの **CComObjectCYourClass** のインスタンスを作成します。  
  
 `CComPolyObject` を使用する利点は集約されます。集約ケースを処理するモジュールで `CComAggObject` と `CComObject` の両方があることを避けるためです。  `CComPolyObject` の単一のオブジェクトは両方を処理します。  したがって、vtable の 1 種類のコピーと関数の 1 のコピーは、モジュールにあります。  、vtable の場合、これは大幅に、モジュールのサイズを抑えることができます。  ただし、ようになります `CComAggObject` と `CComObject`がやや多くのモジュールのサイズで vtable が小さく、集約または非集約オブジェクト用に最適化されていないため `CComPolyObject` を使用して行われます。  
  
 独自のオブジェクトを集約すると、[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) は `CComAggObject` か `CComPolyObject`によって実装されます。  これらのクラスは `CComObjectRootEx` の `OuterQueryInterface`、`OuterAddRef`と `OuterRelease` に不明の外部に転送します `QueryInterface`、`AddRef`と **\[リリース\]** の呼び出しに委任します。  通常、集約オブジェクトを作成するようにクラスのをオーバーライド `CComObjectRootEx::FinalConstruct` 集約オブジェクトを解放するために `CComObjectRootEx::FinalRelease` をオーバーライドします。  
  
 、オブジェクトを集約する必要 **IUnknown** は、`CComObject` か `CComPolyObject`によって実装されます。  この場合、`QueryInterface`の呼び出し、`AddRef`と **\[リリース\]** は `CComObjectRootEx` の `InternalQueryInterface`、`InternalAddRef`と `InternalRelease` に実際の操作を実行するために転送されます。  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [CComAggObject クラス](../../atl/reference/ccomaggobject-class.md)   
 [CComObject クラス](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)