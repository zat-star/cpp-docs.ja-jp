---
title: "_ATL_BASE_MODULE70 構造 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
caps.latest.revision: 15
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
ms.sourcegitcommit: 347e7bf7cd9173fb2815f44fc052ec23ab4055a6
ms.openlocfilehash: 7456d441d7b3fb74f404f29c893c492feab10ed9
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="atlbasemodule70-structure"></a>_ATL_BASE_MODULE70 構造体
ATL を使用する他のプロジェクトで使用されます。  
  
## <a name="syntax"></a>構文  
  
```
struct _ATL_BASE_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInst;
    HINSTANCE m_hInstResource;
    bool m_bNT5orWin98;
    DWORD dwAtlBuildVer;
    GUID* pguidVer;
    CRITICAL_SECTION m_csResource;
    CSimpleArray<HINSTANCE> m_rgResourceInstance;
};
```  
  
## <a name="members"></a>メンバー  
 `cbSize`  
 バージョン管理に使用される、構造体のサイズ。  
  
 `m_hInst`  
 **HInstance** (exe または dll) は、このモジュールのです。  
  
 `m_hInstResource`  
 既定のインスタンスのリソース ハンドル。  
  
 **m_bNT5orWin98**  
 オペレーティング システムのバージョン情報。 ATL で内部的に使用  
  
 **dwAtlBuildVer**  
 ATL のバージョンを格納します。 現在は 0x0700 です。  
  
 **pguidVer**  
 ATL の内部の GUID です。  
  
 **m_csResource**  
 アクセスを同期するために使用、 **m_rgResourceInstance**配列。 ATL で内部的に使用  
  
 **m_rgResourceInstance**  
 ATL が対応であるすべてのリソース インスタンスのリソースを検索するために使用する配列。 ATL で内部的に使用  
  
## <a name="remarks"></a>コメント  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)の typedef と定義`_ATL_BASE_MODULE70`します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
## <a name="see-also"></a>関連項目  
 [構造体](../../atl/reference/atl-structures.md)






