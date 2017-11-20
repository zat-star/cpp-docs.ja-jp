---
title: "集約オブジェクトの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- aggregation [C++], creating aggregated objects
- aggregate objects [C++], creating
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b5446e4eb279e961ba59b5fd0b3713a7f976cef5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="creating-an-aggregated-object"></a>集約オブジェクトの作成
集計デリゲート**IUnknown** 、外部のオブジェクトへのポインターを提供する、呼び出し**IUnknown**を内部オブジェクトです。  
  
### <a name="to-create-an-aggregated-object"></a>集約オブジェクトを作成するには  
  
1.  追加、 **IUnknown**クラスへのポインターをそのオブジェクトを初期化**NULL**コンス トラクターでします。  
  
2.  オーバーライド[FinalConstruct](../atl/reference/ccomobjectrootex-class.md#finalconstruct)集計を作成します。  
  
3.  使用して、 **IUnknown**ポインターでの 2 番目のパラメーターとして、手順 1. で定義されている、[で定義](reference/com-interface-entry-macros.md#com_interface_entry_aggregate)マクロです。  
  
4.  オーバーライド[FinalRelease](../atl/reference/ccomobjectrootex-class.md#finalrelease)を解放する、 **IUnknown**ポインター。  
  
> [!NOTE]
>  使用して、中に集計されたオブジェクトのインターフェイスを解放するかどうか`FinalConstruct`、追加する必要があります、[アグリゲート](reference/aggregation-and-class-factory-macros.md#declare_protect_final_construct)クラス オブジェクトの定義にマクロです。  
  
## <a name="see-also"></a>関連項目  
 [ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)

