---
title: _ATL_MODULE70 構造 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f189ef58ab83a6e77852c109e6da3ae86dc5555d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
## <a name="see-also"></a>関連項目  
 [構造体](../../atl/reference/atl-structures.md)







