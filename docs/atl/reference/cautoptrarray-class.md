---
title: "CAutoPtrArray クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 58ee329c7a3925fe3a29cf9738670cfa71df6777
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cautoptrarray-class"></a>CAutoPtrArray クラス
このクラスは、スマート ポインターの配列を構築するときに役立つメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <typename E>
class CAutoPtrArray : public CAtlArray<
                        ATL::CAutoPtr<E>,
                        CAutoPtrElementTraits<E>>
```  
  
#### <a name="parameters"></a>パラメーター  
 `E`  
 ポインター型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAutoPtrArray::CAutoPtrArray](#cautoptrarray)|コンストラクターです。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、コンス トラクターを提供し、メソッドからの派生元[CAtlArray](../../atl/reference/catlarray-class.md)と[CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)スマート ポインターを格納するコレクション クラスのオブジェクトの作成を支援するためにします。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CAtlArray`  
  
 `CAutoPtrArray`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="cautoptrarray"></a>CAutoPtrArray::CAutoPtrArray  
 コンストラクターです。  
  
```
CAutoPtrArray() throw();
```  
  
### <a name="remarks"></a>コメント  
 スマート ポインターの配列を初期化します。  
  
## <a name="see-also"></a>関連項目  
 [CAtlArray クラス](../../atl/reference/catlarray-class.md)   
 [CAutoPtrElementTraits クラス](../../atl/reference/cautoptrelementtraits-class.md)   
 [CAutoPtrList クラス](../../atl/reference/cautoptrlist-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

