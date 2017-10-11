---
title: "_ATL_WIN_MODULE70 構造 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 7f521b418b7d179eb506a5e9df2887addec059ef
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
## <a name="see-also"></a>関連項目  
 [構造体](../../atl/reference/atl-structures.md)






