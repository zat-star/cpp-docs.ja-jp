---
title: "_ATL_WIN_MODULE70 構造 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
dev_langs: C++
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 733808006a3c301972c4ab3b3f8de3320d9fde46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atlwinmodule70-structure"></a>_ATL_WIN_MODULE70 構造体
ATL の windowing コードによって使用されます。  
  
## <a name="syntax"></a>構文  
  
```
struct _ATL_WIN_MODULE70 {
    UNIT cbSize; 
    CRITICAL_SECTION m_csWindowCreate;
    _AtlCreateWndData* m_pCreateWndList;
    CSimpleArray<ATOM> m_rgWindowClassAtoms;
};
```  
  
## <a name="members"></a>メンバー  
 `cbSize`  
 バージョン管理に使用される、構造のサイズ。  
  
 `m_csWindowCreate`  
 ウィンドウの登録コードへのアクセスをシリアル化に使用します。 ATL で内部的に使用  
  
 **m_pCreateWndList**  
 Windows をそれらのオブジェクトにバインドするために使用します。 ATL で内部的に使用  
  
 **m_rgWindowClassAtoms**  
 終了時に正しく登録いないことができるように、ウィンドウ クラスの登録を追跡するために使用されます。 ATL で内部的に使用  
  
## <a name="remarks"></a>コメント  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)の typedef として定義された`_ATL_WIN_MODULE70`です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlbase.h  
  
## <a name="see-also"></a>参照  
 [構造体](../../atl/reference/atl-structures.md)





