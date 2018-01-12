---
title: "_ATL_BASE_MODULE70 構造 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
dev_langs: C++
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a85aa23baf294f5f1f4dc2eb49c6004d7633280
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
 バージョン管理に使用される、構造のサイズ。  
  
 `m_hInst`  
 **HInstance**このモジュール (exe または dll) です。  
  
 `m_hInstResource`  
 既定のインスタンスのリソース ハンドル。  
  
 **m_bNT5orWin98**  
 オペレーティング システムのバージョン情報です。 ATL で内部的に使用  
  
 **dwAtlBuildVer**  
 ATL のバージョンを格納します。 現在は 0x0700 です。  
  
 **pguidVer**  
 ATL の内部の GUID です。  
  
 **m_csResource**  
 アクセスを同期するために使用される、 **m_rgResourceInstance**配列。 ATL で内部的に使用  
  
 **m_rgResourceInstance**  
 ATL が対応であるすべてのリソース インスタンスのリソースを検索するために使用する配列。 ATL で内部的に使用  
  
## <a name="remarks"></a>コメント  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)の typedef として定義された`_ATL_BASE_MODULE70`です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcore.h  
  
## <a name="see-also"></a>参照  
 [構造体](../../atl/reference/atl-structures.md)





