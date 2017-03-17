---
title: "CHeapPtr クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHeapPtr
- ATLCORE/ATL::CHeapPtr
- ATLCORE/ATL::CHeapPtr::CHeapPtr
- ATLCORE/ATL::CHeapPtr::Allocate
- ATLCORE/ATL::CHeapPtr::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtr class
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
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
ms.openlocfilehash: 41334cd7497c9e21d1cf047d7ab304864f663758
ms.lasthandoff: 02/24/2017

---
# <a name="cheapptr-class"></a>CHeapPtr クラス
ヒープのポインターを管理するためのスマート ポインター クラスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<typename T, class Allocator=CCRTAllocator>  
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 ヒープに格納されるオブジェクトの型。  
  
 `Allocator`  
 メモリの割り当ては、使用するクラス。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHeapPtr::CHeapPtr](#cheapptr)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CHeapPtr::Allocate](#allocate)|オブジェクトを格納するヒープにメモリを割り当てるには、このメソッドを呼び出します。|  
|[CHeapPtr::Reallocate](#reallocate)|ヒープにメモリを再割り当てするには、このメソッドを呼び出します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CHeapPtr::operator =](#operator_eq)|代入演算子です。|  
  
## <a name="remarks"></a>コメント  
 `CHeapPtr`派生した[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) 、既定では、CRT ルーチン (で[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)) にメモリ割り当てし、解放します。 クラス[CHeapPtrList](../../atl/reference/cheapptrlist-class.md)ヒープ ポインターのリストの構築に使用することがあります。 関連項目[CComHeapPtr](../../atl/reference/ccomheapptr-class.md)、COM メモリ割り当てルーチンを使用します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 `CHeapPtr`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
##  <a name="allocate"></a>CHeapPtr::Allocate  
 オブジェクトを格納するヒープにメモリを割り当てるには、このメソッドを呼び出します。  
  
```
bool Allocate(size_t nElements = 1) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nElements`  
 割り当てるメモリの量を計算するために使用する要素の数。 既定値は 1 です。  
  
### <a name="return-value"></a>戻り値  
 失敗した場合に、メモリが正常である場合は true を返しますが割り当てられます。  
  
### <a name="remarks"></a>コメント  
 アロケーター ルーチンを格納するヒープにメモリ不足のための予約を使用して*nElement*コンス トラクターで定義された型のオブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&77;](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]  
  
##  <a name="cheapptr"></a>CHeapPtr::CHeapPtr  
 コンストラクターです。  
  
```
CHeapPtr() throw();
explicit CHeapPtr(T* p) throw();
CHeapPtr(CHeapPtr<T, Allocator>& p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 既存のヒープ ポインターまたは`CHeapPtr`です。  
  
### <a name="remarks"></a>コメント  
 既存のポインターを使用してヒープのポインターを作成することができます必要に応じて、または`CHeapPtr`オブジェクトです。 その場合、新しい`CHeapPtr`オブジェクトには、新しいポインターとリソースを管理する責任が前提としています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&78;](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]  
  
##  <a name="operator_eq"></a>CHeapPtr::operator =  
 代入演算子。  
  
```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 既存の `CHeapPtr` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 更新されたへの参照を返します`CHeapPtr`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&80;](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]  
  
##  <a name="reallocate"></a>CHeapPtr::Reallocate  
 ヒープにメモリを再割り当てするには、このメソッドを呼び出します。  
  
```
bool Reallocate(size_t nElements) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nElements`  
 新しいに割り当てるメモリの量を計算するための要素数。  
  
### <a name="return-value"></a>戻り値  
 失敗した場合に、メモリが正常である場合は true を返しますが割り当てられます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&79;](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CHeapPtrBase クラス](../../atl/reference/cheapptrbase-class.md)   
 [CCRTAllocator クラス](../../atl/reference/ccrtallocator-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

