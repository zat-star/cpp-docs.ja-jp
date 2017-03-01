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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: c18e1c5a41ef910cfe327fdbdd8d8885ef30a092
ms.lasthandoff: 02/24/2017

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
 呼び出し規則 この構造で使用する場合、[されます](../../atl/reference/idispeventsimpleimpl-class.md)クラスでは、このメンバーでなければなりません**CC_STDCALL**します。 `CC_CDECL`Windows ce のサポートされている唯一のオプションは、`CALLCONV`のフィールド、`_ATL_FUNC_INFO`構造体。 その他の値はサポートされていませんので、動作が定義されていません。  
  
 **vtReturn**  
 関数のバリアント型は、値を返します。  
  
 **nParams**  
 関数パラメーターの数。  
  
 **pVarTypes**  
 関数パラメーターのバリアント型の配列。  
  
## <a name="remarks"></a>コメント  
 内部的には、ATL は、タイプ ライブラリから取得した情報を保持するためにこの構造体を使用します。 使用されるイベント ハンドラーの型情報を提供する場合は、この構造体を直接操作する必要があります、[されます](../../atl/reference/idispeventsimpleimpl-class.md)クラスと[SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7)マクロです。  
  
## <a name="example"></a>例  
 IDL で定義されているディスパッチ インターフェイス メソッドを指定します。  
  
 [!code-cpp[NVC_ATL_Windowing #&139;](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]  
  
 定義して、`_ATL_FUNC_INFO`構造体。  
  
 [!code-cpp[NVC_ATL_Windowing #&140;](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
## <a name="see-also"></a>関連項目  
 [構造体](../../atl/reference/atl-structures.md)   
 [されますクラス](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7)






