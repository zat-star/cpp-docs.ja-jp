---
title: "_pAtlModule |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATLBASE/_pAtlModule
- _pAtlModule
- ATL::_pAtlModule
- ATL._pAtlModule
dev_langs:
- C++
helpviewer_keywords:
- pAtlModule variable
- _pAtlModule variable
ms.assetid: 0ecde3a9-3f4d-4c7b-bb54-713ce05c4777
caps.latest.revision: 13
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: b20c5010616323eac9438223df64af9960192e2b
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="patlmodule"></a>_pAtlModule
現在のモジュールへのポインターを格納するグローバル変数。  
  
## <a name="syntax"></a>構文  
  
```  
__declspec(selectany) CAtlModule* _pAtlModule  
```  
  
## <a name="remarks"></a>コメント  
 このグローバル変数のメソッドは、機能を提供するために使用できますが (現在は使用できない) クラス[CComModule](../../atl/reference/ccommodule-class.md) Visual C 6.0 で提供されます。  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&97;](../../atl/codesnippet/cpp/patlmodule_1.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
## <a name="see-also"></a>関連項目  
 [グローバル変数](../../atl/reference/atl-global-variables.md)




