---
title: "_ATL_MODULE70 構造 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
dev_langs: C++
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c8122f733282fa819c3d789a90e60171ee006e27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atlmodule70-structure"></a>_ATL_MODULE70 構造体
すべての ATL モジュールによって使用されるデータが含まれています。  
  
## <a name="syntax"></a>構文  
  
```
struct _ATL_MODULE70 {
    UINT cbSize;
    LONG m_nLockCnt;
    _ATL_TERMFUNC_ELEM* m_pTermFuncs;
    CComCriticalSection m_csStaticDataInitAndTypeInfo;
};
```  
  
## <a name="members"></a>メンバー  
 `cbSize`  
 バージョン管理に使用される、構造のサイズ。  
  
 `m_nLockCnt`  
 参照カウントをどのくらいの期間、モジュールは続けることを決定します。  
  
 **m_pTermFuncs**  
 ATL のシャット ダウン時に呼び出される登録されている関数をトラックします。  
  
 **m_csStaticDataInitAndTypeInfo**  
 マルチ スレッドの状況で、内部データへのアクセスを調整するために使用します。  
  
## <a name="remarks"></a>コメント  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)の typedef として定義された`_ATL_MODULE70`です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlbase.h  
  
## <a name="see-also"></a>参照  
 [構造体](../../atl/reference/atl-structures.md)







