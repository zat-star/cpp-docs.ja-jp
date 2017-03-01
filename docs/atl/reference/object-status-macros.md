---
title: "オブジェクトの状態に関するマクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
caps.latest.revision: 16
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 433a816b19690f22f482f26f6ab70c73ed102673
ms.lasthandoff: 02/24/2017

---
# <a name="object-status-macros"></a>オブジェクトの状態に関するマクロ
このマクロは、ActiveX コントロールに属しているフラグを設定します。  
  
|||  
|-|-|  
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|設定する、ATL の ActiveX コントロールで使用される、**入ります**フラグ。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  

##  <a name="a-namedeclareolemiscstatusa--declareolemiscstatus"></a><a name="declare_olemisc_status"></a>DECLARE_OLEMISC_STATUS  
 ATL の ActiveX コントロールで使用すると、入りますフラグを設定できます。  
  
```
DECLARE_OLEMISC_STATUS( miscstatus )
```  
  
### <a name="parameters"></a>パラメーター  
 *miscstatus*  
 該当するすべての入りますフラグです。  
  
### <a name="remarks"></a>コメント  
 このマクロは、ActiveX コントロールの入りますフラグの設定に使用されます。 参照してください[IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521)詳細です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&124;](../../atl/codesnippet/cpp/object-status-macros_1.h)]  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)

