---
title: "CComQIPtr クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComQIPtr
- ATL::CComQIPtr
- CComQIPtr
dev_langs:
- C++
helpviewer_keywords:
- CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
caps.latest.revision: 19
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e2060a0be3f9780191c316c2df41115e66033d4d
ms.lasthandoff: 02/24/2017

---
# <a name="ccomqiptr-class"></a>CComQIPtr クラス
COM インターフェイス ポインターを管理するためのスマート ポインター クラスです。  
  
## <a name="syntax"></a>構文  
  
```
template<class T, const IID* piid= &__uuidof(T)>  
class CComQIPtr: public CComPtr<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 格納されるポインターの型を指定する COM インターフェイスです。  
  
 `piid`  
 IID へのポインター`T`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComQIPtr::CComQIPtr](#ccomqiptr)|コンストラクターです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CComQIPtr::operator =](#operator_eq)|メンバーのポインターへのポインターを割り当てます。|  
  
## <a name="remarks"></a>コメント  
 ATL では、`CComQIPtr`と[CComPtr](../../atl/reference/ccomptr-class.md)から派生する COM インターフェイス ポインターを管理する[CComPtrBase](../../atl/reference/ccomptrbase-class.md)します。 クラスは両方とも実行自動の参照カウントの呼び出しを通じて`AddRef`と**リリース**します。 オーバー ロードされた演算子は、ポインターの操作を処理します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 [CComPtr](../../atl/reference/ccomptr-class.md)  
  
 `CComQIPtr`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcomcli.h  
  
##  <a name="a-nameccomqiptra--ccomqiptrccomqiptr"></a><a name="ccomqiptr"></a>CComQIPtr::CComQIPtr  
 コンストラクターです。  
  
```
CComQIPtr() throw();
CComQIPtr(T* lp) throw();
CComQIPtr(IUnknown* lp) throw();
CComQIPtr(const CComQIPtr<T, piid>& lp) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lp`  
 インターフェイス ポインターを初期化するために使用します。  
  
 `T`  
 COM インターフェイスです。  
  
 `piid`  
 IID へのポインター`T`します。  
  
##  <a name="a-nameoperatoreqa--ccomqiptroperator-"></a><a name="operator_eq"></a>CComQIPtr::operator =  
 代入演算子です。  
  
```
T* operator= (T* lp) throw();
T* operator= (const CComQIPtr<T, piid>& lp) throw();
T* operator= (IUnknown* lp) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lp`  
 インターフェイス ポインターを初期化するために使用します。  
  
 `T`  
 COM インターフェイスです。  
  
 `piid`  
 IID へのポインター`T`します。  
  
### <a name="return-value"></a>戻り値  
 更新後にポインターを返す`CComQIPtr`オブジェクトです。  
  
## <a name="see-also"></a>関連項目  
 [CComPtr::CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)   
 [CComQIPtr::CComQIPtr](#ccomqiptr)   
 [CComPtrBase クラス](../../atl/reference/ccomptrbase-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComQIPtrElementTraits クラス](../../atl/reference/ccomqiptrelementtraits-class.md)

