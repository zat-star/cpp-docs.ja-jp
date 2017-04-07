---
title: "_ATL_FUNC_INFO 構造 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
dev_langs:
- C++
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
caps.latest.revision: 21
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 7bc607931c486f3dd7a398b277048db77e9b2f62
ms.lasthandoff: 03/31/2017

---
# <a name="atlfuncinfo-structure"></a>_ATL_FUNC_INFO 構造体
ディスパッチ インターフェイスでメソッドまたはプロパティを記述するために使用する型情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```
struct _ATL_FUNC_INFO {
    CALLCONV cc;
    VARTYPE vtReturn;
    SHORT nParams;
    VARTYPE pVarTypes[_ATL_MAX_VARTYPES];
};
```  
  
## <a name="members"></a>メンバー  
 **[cc]**  
 呼び出し規則 この構造体を使用する場合、[されます](../../atl/reference/idispeventsimpleimpl-class.md)このメンバーである必要がありますクラス、 **CC_STDCALL**です。 `CC_CDECL`Windows CE でサポートされる唯一のオプションは、`CALLCONV`のフィールド、`_ATL_FUNC_INFO`構造体。 その他の値はサポートされていないためその動作が定義されていません。  
  
 **vtReturn**  
 関数のバリアント型は、値を返します。  
  
 **nParams**  
 関数パラメーターの数。  
  
 **pVarTypes**  
 関数のパラメーターのバリアント型の配列。  
  
## <a name="remarks"></a>コメント  
 内部的には、ATL は、タイプ ライブラリから取得した情報を保持するためにこの構造を使用します。 使用するイベント ハンドラーの型情報を提供する場合は、この構造体を直接操作する必要があります、[されます](../../atl/reference/idispeventsimpleimpl-class.md)クラスと[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)マクロです。  
  
## <a name="example"></a>例  
 IDL で定義されたディスパッチ インターフェイス メソッドを指定します。  
  
 [!code-cpp[NVC_ATL_Windowing # 139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]  
  
 定義して、`_ATL_FUNC_INFO`構造体。  
  
 [!code-cpp[NVC_ATL_Windowing # 140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
## <a name="see-also"></a>関連項目  
 [構造体](../../atl/reference/atl-structures.md)   
 [されますクラス](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)






