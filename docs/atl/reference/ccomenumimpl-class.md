---
title: "CComEnumImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComEnumImpl
- ATL::CComEnumImpl
- CComEnumImpl
dev_langs:
- C++
helpviewer_keywords:
- CComEnumImpl class
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 6dc6a8ed6a318642efe58dfb94835d45b2163b54
ms.lasthandoff: 02/24/2017

---
# <a name="ccomenumimpl-class"></a>CComEnumImpl クラス
このクラスは、配列内の列挙されている項目が格納されている COM 列挙子インターフェイスの実装を提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Base,
    const IID* piid, class T, class Copy>  
class ATL_NO_VTABLE CComEnumImpl : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 COM の列挙子 ([として](https://msdn.microsoft.com/library/ms680089.aspx)) インターフェイス。  
  
 `piid`  
 列挙子インターフェイスのインターフェイス ID へのポインター。  
  
 `T`  
 列挙子インターフェイスによって公開される項目の種類。  
  
 `Copy`  
 同種[コピー ポリシー クラス](../../atl/atl-copy-policy-classes.md)します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComEnumImpl::CComEnumImpl](#ccomenumimpl)|コンストラクターです。|  
|[CComEnumImpl:: ~ CComEnumImpl](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComEnumImpl::Clone](#clone)|実装[IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx)します。|  
|[保ちます](#init)|列挙子を初期化します。|  
|[CComEnumImpl::Next](#next)|実装[IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx)します。|  
|[CComEnumImpl::Reset](#reset)|実装[IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx)します。|  
|[より](#skip)|実装[IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx)します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComEnumImpl::m_begin](#m_begin)|配列の最初の項目へのポインター。|  
|[CComEnumImpl::m_dwFlags](#m_dwflags)|を通じて渡されるコピー フラグ`Init`します。|  
|[CComEnumImpl::m_end](#m_end)|配列の最後の項目の次の場所へのポインター。|  
|[CComEnumImpl::m_iter](#m_iter)|配列内の現在の項目へのポインター。|  
|[CComEnumImpl::m_spUnk](#m_spunk)|**IUnknown**列挙されているコレクションを提供するオブジェクトのポインター。|  
  
## <a name="remarks"></a>コメント  
 `CComEnumImpl`配列内の列挙されている項目が格納されている COM 列挙子インターフェイスの実装を提供します。 このクラスに類似しています、`IEnumOnSTLImpl`クラス、列挙子インターフェイスの実装を提供する C++ 標準ライブラリのコンテナーに基づいています。  
  
> [!NOTE]
>  さらに違いの詳細`CComEnumImpl`と`IEnumOnSTLImpl`を参照してください[保ちます](#init)します。  
  
 通常、*いない*このインターフェイスの実装から派生させて、独自の列挙子クラスを作成する必要があります。 配列に基づいた ATL が指定した列挙子を使用する場合は、インスタンスを作成する方が一般的[上記](../../atl/reference/ccomenum-class.md)します。  
  
 ただし、(たとえば、1 つだけでなく、列挙子インターフェイスのインターフェイスを公開する) カスタム列挙子を提供する必要がある場合は、このクラスから派生できます。 このような状況では通常をオーバーライドする必要があります、 [CComEnumImpl::Clone](#clone)メソッドを独自の実装を提供します。  
  
 詳細については、次を参照してください。 [ATL のコレクションと列挙子](../../atl/atl-collections-and-enumerators.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Base`  
  
 `CComEnumImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="a-nameccomenumimpla--ccomenumimplccomenumimpl"></a><a name="ccomenumimpl"></a>CComEnumImpl::CComEnumImpl  
 コンストラクターです。  
  
```
CComEnumImpl();
```  
  
##  <a name="a-namedtora--ccomenumimplccomenumimpl"></a><a name="dtor"></a>CComEnumImpl:: ~ CComEnumImpl  
 デストラクターです。  
  
```
~CComEnumImpl();
```  
  
##  <a name="a-nameinita--ccomenumimplinit"></a><a name="init"></a>保ちます  
 クライアントに返す列挙子インターフェイスへのポインターを渡す前に、このメソッドを呼び出す必要があります。  
  
```
HRESULT Init(
    T* begin,
    T* end,
    IUnknown* pUnk,
    CComEnumFlags flags = AtlFlagNoCopy);
```  
  
### <a name="parameters"></a>パラメーター  
 *begin*  
 列挙するアイテムを含む配列の最初の要素へのポインター。  
  
 `end`  
 列挙するアイテムを含む配列の最後の要素の次の場所へのポインター。  
  
 *pUnk*  
 [in]**IUnknown**する必要がある alive 列挙子の有効期間中にオブジェクトのポインター。 渡す**NULL**このようなオブジェクトが存在しない場合。  
  
 `flags`  
 列挙子が配列の所有権を取得する必要があるかどうか、またはそのコピーを作成かどうかを指定するフラグ。 使用可能な値は次のとおりです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 このメソッドを&1; 回だけ呼び出す: 列挙子を初期化し、それを使用して、破棄することです。  
  
 別のオブジェクトに保持されている配列内の項目にポインターを渡す場合 (データをコピーする列挙子を確認しない) 場合、行うこともできます、 *pUnk*パラメーターをオブジェクトとを保持する配列を使用できること、列挙子では、その必要がある限りことを確認します。 列挙子を維持するオブジェクトの COM の参照を保持するだけです。 列挙子が破棄されるときに、COM 参照が自動的に解放します。  
  
 `flags`パラメーターでは、列挙子が渡された配列の要素を処理する方法を指定することができます。 `flags`値のいずれかを実行、**使用**列挙型を次に示します。  
  
 `enum CComEnumFlags`  
  
 `{`  
  
 `AtlFlagNoCopy = 0,`  
  
 `AtlFlagTakeOwnership = 2, // BitOwn`  
  
 `AtlFlagCopy = 3           // BitOwn | BitCopy`  
  
 `};`  
  
 **AtlFlagNoCopy**配列の有効期間が列挙子によって制御されていないことを意味します。 この場合は、いずれか、配列となりますで識別されるオブジェクトが静的または*pUnk*不要になったときに、配列を解放する責任があります。  
  
 **AtlFlagTakeOwnership**は配列の破棄は、列挙子によって制御することを意味します。 この場合、配列する必要がありますが動的に割り当てたを使用して**新しい**します。 列挙子は、デストラクターで配列を削除します。 渡すは通常、 **NULL**の*pUnk*、何らかの理由の列挙子の破棄を通知する必要がある場合も、有効なポインターを渡すことができます。  
  
 **AtlFlagCopy**新しい配列が渡された配列をコピーすることによって作成されることを意味`Init`します。 新しい配列の有効期間は、列挙子によって制御されます。 列挙子は、デストラクターで配列を削除します。 渡すは通常、 **NULL**の*pUnk*、何らかの理由の列挙子の破棄を通知する必要がある場合も、有効なポインターを渡すことができます。  
  
> [!NOTE]
>  このメソッドのプロトタイプが型として、配列要素を指定する**T**ここで、 **T**クラスをテンプレート パラメーターとして定義されました。 これは、COM インターフェイスのメソッドを使用して公開されている同じ種類[CComEnumImpl::Next](#next)します。 このこととは異なり[つまり](../../atl/reference/ienumonstlimpl-class.md)、このクラスは、別の記憶域をサポートしておらず、データ型を公開します。 配列内の要素のデータ型は、COM インターフェイスで公開されているデータ型と同じである必要があります。  
  
##  <a name="a-nameclonea--ccomenumimplclone"></a><a name="clone"></a>CComEnumImpl::Clone  
 このメソッドの実装を提供する、 [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx)型のオブジェクトを作成することでメソッド`CComEnum`、同じ配列と、現在のオブジェクトで使用される反復子で初期化し、新しく作成されたオブジェクトでインターフェイスが返されます。  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppEnum`  
 [out]新しく作成されたオブジェクトの列挙子インターフェイスは、現在の列挙子から複製されます。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 複製された列挙子しないように指定して、独自に注意してください、元の列挙子によって使用されるデータのコピー (または所有権の取得)。 必要に応じて、複製された列挙子は元の列挙子を生かしておく (COM の参照を使用) 必要がある限り、データが使用できることを確認します。  
  
##  <a name="a-namemspunka--ccomenumimplmspunk"></a><a name="m_spunk"></a>CComEnumImpl::m_spUnk  
 このスマート ポインターに渡されるオブジェクトの参照を保持する[保ちます](#init)、列挙子の有効期間中に生きてことがあることを確認します。  
  
```
CComPtr<IUnknown> m_spUnk;
```  
  
##  <a name="a-namembegina--ccomenumimplmbegin"></a><a name="m_begin"></a>CComEnumImpl::m_begin  
 列挙するアイテムを含む配列の最後の要素の次の場所へのポインター。  
  
```
T* m_begin;
```  
  
##  <a name="a-namemenda--ccomenumimplmend"></a><a name="m_end"></a>CComEnumImpl::m_end  
 列挙するアイテムを含む配列の最初の要素へのポインター。  
  
```
T* m_end;
```  
  
##  <a name="a-namemitera--ccomenumimplmiter"></a><a name="m_iter"></a>CComEnumImpl::m_iter  
 列挙するアイテムを含む配列の現在の要素へのポインター。  
  
```
T* m_iter;
```  
  
##  <a name="a-namemdwflagsa--ccomenumimplmdwflags"></a><a name="m_dwflags"></a>CComEnumImpl::m_dwFlags  
 渡される、フラグ[保ちます](#init)します。  
  
```
DWORD m_dwFlags;
```  
  
##  <a name="a-namenexta--ccomenumimplnext"></a><a name="next"></a>CComEnumImpl::Next  
 このメソッドの実装を提供する、 [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx)メソッドです。  
  
```
STDMETHOD(Next)(ULONG celt, T* rgelt, ULONG* pceltFetched);
```  
  
### <a name="parameters"></a>パラメーター  
 `celt`  
 [in]要求された要素の数。  
  
 `rgelt`  
 [out]要素を格納する配列。  
  
 `pceltFetched`  
 [out]実際に返される要素の数`rgelt`します。 これより小さい`celt`場合よりも少ない`celt`要素がリストに残っています。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="a-namereseta--ccomenumimplreset"></a><a name="reset"></a>CComEnumImpl::Reset  
 このメソッドの実装を提供する、 [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx)メソッドです。  
  
```
STDMETHOD(Reset)(void);
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="a-nameskipa--ccomenumimplskip"></a><a name="skip"></a>より  
 このメソッドの実装を提供する、 [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx)メソッドです。  
  
```
STDMETHOD(Skip)(ULONG celt);
```  
  
### <a name="parameters"></a>パラメーター  
 `celt`  
 [in]スキップする要素の数。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 場合、E_INVALIDARG を返します`celt`が&0; の場合より小さい場合は S_FALSE を返します`celt`要素が返されると、それ以外の場合は S_OK を返します。  
  
## <a name="see-also"></a>関連項目  
 [つまりクラス](../../atl/reference/ienumonstlimpl-class.md)   
 [上記のクラス](../../atl/reference/ccomenum-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

