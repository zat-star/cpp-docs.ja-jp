---
title: "_ATL_COM_MODULE70 構造 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::_ATL_COM_MODULE70
- ATL._ATL_COM_MODULE70
- _ATL_COM_MODULE70
dev_langs: C++
helpviewer_keywords:
- _ATL_COM_MODULE70 structure
- ATL_COM_MODULE70 structure
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a269820c5a0965553989bc57d7c239aa95e527ef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="atlcommodule70-structure"></a>_ATL_COM_MODULE70 構造体
ATL で COM に関連するコードで使用されます。  
  
## <a name="syntax"></a>構文  
  
```
struct _ATL_COM_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInstTypeLib;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;
    CRITICAL_SECTION m_csObjMap;
};
```  
  
## <a name="members"></a>メンバー  
 `cbSize`  
 バージョン管理に使用される、構造のサイズ。  
  
 `m_hInstTypeLib`  
 このモジュールのタイプ ライブラリへのハンドルのインスタンス。  
  
 **m_ppAutoObjMapFirst**  
 このモジュールのオブジェクトのマップ エントリの先頭を示す、配列要素のアドレスです。  
  
 **m_ppAutoObjMapLast**  
 このモジュールのオブジェクトのマップ エントリの終了を示す、配列要素のアドレスです。  
  
 `m_csObjMap`  
 オブジェクト マップ エントリへのアクセスをシリアル化するクリティカル セクション。 ATL で内部的に使用  
  
## <a name="remarks"></a>コメント  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)の typedef として定義された`_ATL_COM_MODULE70`です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
## <a name="see-also"></a>関連項目  
 [構造体](../../atl/reference/atl-structures.md)





