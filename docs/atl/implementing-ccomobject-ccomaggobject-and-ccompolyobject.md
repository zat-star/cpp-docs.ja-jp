---
title: "CComObject、CComAggObject、および CComPolyObject の実装 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CComPolyObject"
  - "CComAggObject"
  - "CComObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAggObject クラス"
  - "CComObject クラス, 実装"
  - "CComPolyObject クラス, 実装"
  - "CreateInstance メソッド"
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComObject、CComAggObject、および CComPolyObject の実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テンプレートは [CComObject](../atl/reference/ccomobject-class.md)、[CComAggObject](../atl/reference/ccomaggobject-class.md)を並べ替え、[CComPolyObject](../atl/reference/ccompolyobject-class.md) は継承チェーンの最派生クラスは常にです。  これは **IUnknown**のすべてのメソッドを処理する必要があります: `QueryInterface`、`AddRef`と **\[リリース\]**。  また \(集約オブジェクトに対して使用された場合\)、`CComAggObject` と `CComPolyObject` は内側の演算子に必要な `QueryInterface` の特別な参照カウント、およびセマンティクスを提供します。  
  
 `CComObject`、`CComAggObject`、または `CComPolyObject` が使用されるかは次のマクロの 1 文字 \(またはなし\) 宣言するかによります:  
  
|マクロ|効果|  
|---------|--------|  
|`DECLARE_NOT_AGGREGATABLE`|`CComObject`を常に使用します。|  
|`DECLARE_AGGREGATABLE`|あるオブジェクトが `CComObject` 集計する場合 `CComAggObject` を使用します。  `CComCoClass` は **DECLARE\_\*\_AGGREGATABLE** のマクロはいずれも、クラスで宣言されていない場合は、このマクロを、これが既定の設定が含まれています。|  
|`DECLARE_ONLY_AGGREGATABLE`|`CComAggObject`を常に使用します。  オブジェクトが集約するエラーを返します。|  
|`DECLARE_POLY_AGGREGATABLE`|ATL は **IClassFactory::CreateInstance** が呼び出されたときに **CComPolyObjectCYourClass** のインスタンスを作成します。  作成時に、外側の不明の値がチェックされます。  これは **null**場合、**IUnknown** は集約オブジェクトに実装されます。  外側の **null**が不明である、**IUnknown** は集約オブジェクトに実装されます。|  
  
 `CComAggObject` と `CComObject` を使用する利点は **IUnknown** の実装が作成されたオブジェクトの種類用に最適化されます。  たとえば、非集約オブジェクトは集約オブジェクトは外側の不明に内部の未知の参照カウントとポインターの両方を必要なだけが、参照カウントが必要です。  
  
 `CComPolyObject` を使用する利点は集約されます。集約ケースを処理するモジュールで `CComAggObject` と `CComObject` の両方があることを避けるためです。  `CComPolyObject` の単一のオブジェクトは両方を処理します。  これは、vtable の 1 種類のコピーと関数の 1 のコピーは、モジュールであることを意味します。  、vtable の場合、これは大幅に、モジュールのサイズを抑えることができます。  ただし、ようになります `CComAggObject` と `CComObject`がやや多くのモジュールのサイズで vtable が小さく、集約または非集約オブジェクト用に最適化されていないため `CComPolyObject` を使用して行われます。  
  
## 参照  
 [ATL COM オブジェクトの基本事項](../atl/fundamentals-of-atl-com-objects.md)   
 [集約とクラス ファクトリに関するマクロ](../atl/reference/aggregation-and-class-factory-macros.md)