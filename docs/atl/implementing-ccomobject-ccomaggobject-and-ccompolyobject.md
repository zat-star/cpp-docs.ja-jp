---
title: "CComObject と実装すると、および CComPolyObject |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CComPolyObject
- CComAggObject
- CComObject
dev_langs: C++
helpviewer_keywords:
- CComPolyObject class, implementing
- CreateInstance method
- CComAggObject class
- CComObject class, implementing
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 54f237a629c4af9ea7ae30aeca21c03786abcd97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-ccomobject-ccomaggobject-and-ccompolyobject"></a>CComObject と実装すると、および CComPolyObject
テンプレート クラス[CComObject](../atl/reference/ccomobject-class.md)、[すると](../atl/reference/ccomaggobject-class.md)、および[CComPolyObject](../atl/reference/ccompolyobject-class.md)継承チェーン内の最も派生クラスでは常にします。 すべてのメソッドは、処理する責任は**IUnknown**: `QueryInterface`、 `AddRef`、および**リリース**です。 さらに、`CComAggObject`と`CComPolyObject`(集約オブジェクトの使用) する場合、特別な参照カウントを提供および`QueryInterface`内部の不明なのために必要なセマンティクスです。  
  
 かどうか`CComObject`、 `CComAggObject`、または`CComPolyObject`使用以下のマクロのいずれか (またはなし) を宣言するかどうかによって異なります。  
  
|マクロ|効果|  
|-----------|------------|  
|`DECLARE_NOT_AGGREGATABLE`|常に使用`CComObject`です。|  
|`DECLARE_AGGREGATABLE`|使用して`CComAggObject`集約オブジェクトの場合と`CComObject`されていない場合。 `CComCoClass`このマクロを含むようにない場合、 **DECLARE_\*_AGGREGATABLE**マクロは、宣言されたクラスでは、これは既定値になります。|  
|`DECLARE_ONLY_AGGREGATABLE`|常に使用`CComAggObject`です。 オブジェクトが集計されない場合は、エラーを返します。|  
|`DECLARE_POLY_AGGREGATABLE`|ATL のインスタンスを作成する**CComPolyObject\<CYourClass >**とき**IClassFactory::CreateInstance**と呼びます。 作成中に、外側の不明な値がチェックされます。 場合は**NULL**、 **IUnknown**非集約オブジェクトには実装されています。 外側の unknown がない場合**NULL**、 **IUnknown**集約オブジェクトには実装されています。|  
  
 使用する利点`CComAggObject`と`CComObject`の実装は**IUnknown**作成されるオブジェクトの種類に適しています。 たとえば、集約オブジェクトには、内部の不明な参照カウントと外部へのポインターの両方が必要があるときに非集約オブジェクトによって参照カウントがのみが必要です。  
  
 使用する利点`CComPolyObject`両方を避けることが`CComAggObject`と`CComObject`モジュールに、集計と非集計のケースに対処します。 1 つ`CComPolyObject`オブジェクトは両方のケースを処理します。 つまり、モジュールに vtable の 1 つだけのコピーと、関数のうちの 1 つのコピーが存在します。 Vtable が大きい場合は、モジュールのサイズを大幅に縮小このできます。 ただし、vtable が小さい場合を使用して`CComPolyObject`には、集計または非集約オブジェクトは、最適化されていないために、わずかに大きくモジュールのサイズになりますが`CComAggObject`と`CComObject`です。  
  
## <a name="see-also"></a>参照  
 [ATL COM オブジェクトの基本事項](../atl/fundamentals-of-atl-com-objects.md)   
 [集計とクラス ファクトリに関するマクロ](../atl/reference/aggregation-and-class-factory-macros.md)

