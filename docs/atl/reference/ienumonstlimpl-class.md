---
title: "つまりクラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl::Clone
- ATLCOM/ATL::IEnumOnSTLImpl::Init
- ATLCOM/ATL::IEnumOnSTLImpl::Next
- ATLCOM/ATL::IEnumOnSTLImpl::Reset
- ATLCOM/ATL::IEnumOnSTLImpl::Skip
- ATLCOM/ATL::IEnumOnSTLImpl::m_iter
- ATLCOM/ATL::IEnumOnSTLImpl::m_pcollection
- ATLCOM/ATL::IEnumOnSTLImpl::m_spUnk
dev_langs:
- C++
helpviewer_keywords:
- IEnumOnSTLImpl class
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
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
ms.openlocfilehash: 291993d2914d6082b69bfe7816d7c805e93494c4
ms.lasthandoff: 02/24/2017

---
# <a name="ienumonstlimpl-class"></a>つまりクラス
このクラスは、C++ 標準ライブラリ コレクションに基づく列挙子インターフェイスを定義します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>  
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 COM の列挙子 ([として](https://msdn.microsoft.com/library/ms680089.aspx)) インターフェイス。  
  
 `piid`  
 列挙子インターフェイスのインターフェイス ID へのポインター。  
  
 `T`  
 列挙子インターフェイスによって公開される項目の種類。  
  
 `Copy`  
 A[コピー ポリシー クラス](../../atl/atl-copy-policy-classes.md)します。  
  
 `CollType`  
 C++ 標準ライブラリのコンテナー クラスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IEnumOnSTLImpl::Clone](#clone)|実装[IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx)します。|  
|[保ちます](#init)|列挙子を初期化します。|  
|[IEnumOnSTLImpl::Next](#next)|実装[IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx)します。|  
|[IEnumOnSTLImpl::Reset](#reset)|実装[IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx)します。|  
|[IEnumOnSTLImpl::Skip](#skip)|実装[IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx)します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[IEnumOnSTLImpl::m_iter](#m_iter)|コレクション内の列挙子の現在位置を表す反復子。|  
|[IEnumOnSTLImpl::m_pcollection](#m_pcollection)|列挙されるアイテムを保持する C++ 標準ライブラリのコンテナーへのポインター。|  
|[IEnumOnSTLImpl::m_spUnk](#m_spunk)|**IUnknown**コレクションを提供するオブジェクトのポインター。|  
  
## <a name="remarks"></a>コメント  
 `IEnumOnSTLImpl`C++ 標準ライブラリと互換性のあるコンテナー内の列挙されている項目が格納されている COM 列挙子インターフェイスの実装を提供します。 このクラスに似ていますが、 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)配列に基づいて、クラス、列挙子インターフェイスの実装を提供します。  
  
> [!NOTE]
>  参照してください[保ちます](../../atl/reference/ccomenumimpl-class.md#init)の違いをさらに詳細`CComEnumImpl`と`IEnumOnSTLImpl`です。  
  
 通常、*いない*このインターフェイスの実装から派生させて、独自の列挙子クラスを作成する必要があります。 C++ 標準ライブラリのコンテナーに基づく ATL が指定した列挙子を使用する場合は、インスタンスを作成する方が一般的[CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)から派生することで列挙子が返すコレクション クラスを作成したり[ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)します。  
  
 ただし、(たとえば、1 つだけでなく、列挙子インターフェイスのインターフェイスを公開する) カスタム列挙子を提供する必要がある場合は、このクラスから派生できます。 このような状況では通常をオーバーライドする必要があります、[複製](#clone)メソッドを独自の実装を提供します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Base`  
  
 `IEnumOnSTLImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="init"></a>保ちます  
 列挙子を初期化します。  
  
```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkForRelease`  
 [in]**IUnknown**する必要がある alive 列挙子の有効期間中にオブジェクトのポインター。 渡す**NULL**このようなオブジェクトが存在しない場合。  
  
 `collection`  
 列挙されるアイテムを保持する C++ Standard Library コンテナーへの参照。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 渡した場合`Init`コレクションへの参照が別のオブジェクトに保持されていることを使用する、`pUnkForRelease`パラメーターを使用できるように、オブジェクトおよび保持しているコレクションの列挙子では、その必要がある限りです。  
  
 クライアントに返す列挙子インターフェイスへのポインターを渡す前に、このメソッドを呼び出す必要があります。  
  
##  <a name="clone"></a>IEnumOnSTLImpl::Clone  
 このメソッドの実装を提供する、 [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx)型のオブジェクトを作成することでメソッド`CComEnumOnSTL`、同じコレクションと、現在のオブジェクトで使用される反復子で初期化し、新しく作成されたオブジェクトでインターフェイスが返されます。  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppEnum`  
 [out]新しく作成されたオブジェクトの列挙子インターフェイスは、現在の列挙子から複製されます。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="m_spunk"></a>IEnumOnSTLImpl::m_spUnk  
 **IUnknown**コレクションを提供するオブジェクトのポインター。  
  
```
CComPtr<IUnknown> m_spUnk;
```  
  
### <a name="remarks"></a>コメント  
 このスマート ポインターに渡されるオブジェクトの参照を保持する[保ちます](#init)、列挙子の有効期間中に生きてことがあることを確認します。  
  
##  <a name="m_pcollection"></a>IEnumOnSTLImpl::m_pcollection  
 このメンバーは、列挙子インターフェイスの実装で処理するデータを提供するコレクションを指します。  
  
```
CollType* m_pcollection;
```  
  
### <a name="remarks"></a>コメント  
 このメンバーはへの呼び出しによって初期化[保ちます](#init)します。  
  
##  <a name="m_iter"></a>IEnumOnSTLImpl::m_iter  
 このメンバーは、コレクション内の現在位置をマークし、後続の要素に移動するために使用する反復子を保持します。  
  
```
CollType::iterator m_iter;
```  
  
##  <a name="next"></a>IEnumOnSTLImpl::Next  
 このメソッドの実装を提供する、 [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx)メソッドです。  
  
```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```  
  
### <a name="parameters"></a>パラメーター  
 `celt`  
 [in]要求された要素の数。  
  
 `rgelt`  
 [out]要素を使用して格納する配列。  
  
 `pceltFetched`  
 [out]実際に返される要素の数`rgelt`します。 これより小さい`celt`場合よりも少ない`celt`要素は、一覧に残っています。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="reset"></a>IEnumOnSTLImpl::Reset  
 このメソッドの実装を提供する、 [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx)メソッドです。  
  
```
STDMETHOD(Reset)(void);
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="skip"></a>IEnumOnSTLImpl::Skip  
 このメソッドの実装を提供する、 [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx)メソッドです。  
  
```
STDMETHOD(Skip)(ULONG celt);
```  
  
### <a name="parameters"></a>パラメーター  
 `celt`  
 [in]スキップする要素の数。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

