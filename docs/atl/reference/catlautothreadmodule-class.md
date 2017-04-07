---
title: "残さクラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModule
- atlbase/ATL::CAtlAutoThreadModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 159b2f13dc573262bfab3a2e19209b29e3eaf5a5
ms.lasthandoff: 03/31/2017

---
# <a name="catlautothreadmodule-class"></a>残さクラス
このクラスは、スレッド プール、アパートメント モデルの COM サーバーを実装します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```  
  
## <a name="remarks"></a>コメント  
 `CAtlAutoThreadModule`派生した[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)し、スレッド プール、アパートメント モデルの COM サーバーを実装します。 `CAtlAutoThreadModule`使用して[CComApartment](../../atl/reference/ccomapartment-class.md)モジュール内の各スレッド アパートメントを管理します。  
  
 使用する必要があります、 [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread)を指定するオブジェクトのクラス定義でマクロ[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)クラス ファクトリとして。 派生したクラスの 1 つのインスタンスを追加する必要があります、`CAtlAutoThreadModuleT`など`CAtlAutoThreadModule`です。 例:  
  
 `CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`  
  
> [!NOTE]
>  このクラスは廃止された置換[は](../../atl/reference/ccomautothreadmodule-class.md)クラスです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IAtlAutoThreadModule`  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 `CAtlAutoThreadModule`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
## <a name="see-also"></a>関連項目  
 [CAtlAutoThreadModuleT クラス](../../atl/reference/catlautothreadmodulet-class.md)   
 [IAtlAutoThreadModule クラス](../../atl/reference/iatlautothreadmodule-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [モジュール クラス](../../atl/atl-module-classes.md)

