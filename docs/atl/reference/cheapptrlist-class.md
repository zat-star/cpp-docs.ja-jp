---
title: "CHeapPtrList クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList::CHeapPtrList
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtrList class
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
caps.latest.revision: 20
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 9acf18d0e0a72f27a335cefca81341c95d530ae5
ms.lasthandoff: 02/24/2017

---
# <a name="cheapptrlist-class"></a>CHeapPtrList クラス
このクラスは、ヒープのポインターのリストを構築するときに役立つメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<typename E, class Allocator = ATL::CCRTAllocator>  
class CHeapPtrList 
   : public CAtlList<ATL::CHeapPtr<E, Allocator>,
                     CHeapPtrElementTraits<E, Allocator>>
```  
  
#### <a name="parameters"></a>パラメーター  
 `E`  
 コレクション クラスに格納されるオブジェクトの型。  
  
 `Allocator`  
 メモリの割り当ては、使用するクラス。 既定値は[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHeapPtrList::CHeapPtrList](#cheapptrlist)|コンストラクターです。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、コンス トラクターを提供し、メソッドからの派生元[CAtlList](../../atl/reference/catllist-class.md)と[CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)ヒープ ポインターを格納するコレクション クラスのオブジェクトの作成を支援するためにします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CHeapPtrList`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="cheapptrlist"></a>CHeapPtrList::CHeapPtrList  
 コンストラクターです。  
  
```
CHeapPtrList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBlockSize`  
 ブロック サイズ。  
  
### <a name="remarks"></a>コメント  
 ブロック サイズは、新しい要素が必要なときに割り当てられたメモリの量の測定値です。 ブロック サイズの増加はメモリ割り当てルーチンの呼び出しを減らすためより多くのリソースを使用します。  
  
## <a name="see-also"></a>関連項目  
 [CAtlList クラス](../../atl/reference/catllist-class.md)   
 [CHeapPtr クラス](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrElementTraits クラス](../../atl/reference/cheapptrelementtraits-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

