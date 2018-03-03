---
title: "オブジェクトの状態に関するマクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
dev_langs:
- C++
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1139c30fa5d23f3320cef76d09fb5bd86c8c4bc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="object-status-macros"></a>オブジェクトの状態に関するマクロ
このマクロは、ActiveX コントロールに属しているフラグを設定します。  
  
|||  
|-|-|  
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|設定する、ATL の ActiveX コントロールで使用される、**入ります**フラグ。|  

## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcom.h  

##  <a name="declare_olemisc_status"></a>DECLARE_OLEMISC_STATUS  
 ATL の ActiveX コントロールで使用すると、入りますフラグを設定できます。  
  
```
DECLARE_OLEMISC_STATUS( miscstatus )
```  
  
### <a name="parameters"></a>パラメーター  
 *miscstatus*  
 該当するすべての入りますフラグです。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用すると、ActiveX コントロールの入りますフラグを設定します。 参照してください[IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521)詳細についてはします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]  
  
## <a name="see-also"></a>参照  
 [[マクロ]](../../atl/reference/atl-macros.md)
