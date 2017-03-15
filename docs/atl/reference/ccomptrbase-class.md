---
title: "CComPtrBase クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComPtrBase
- ATL::CComPtrBase<T>
- ATL.CComPtrBase<T>
- ATL::CComPtrBase
- CComPtrBase
dev_langs:
- C++
helpviewer_keywords:
- CComPtrBase class
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
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
ms.openlocfilehash: 28207e483b0bf56b9e3e98f487d174b8ae47e9e7
ms.lasthandoff: 02/24/2017

---
# <a name="ccomptrbase-class"></a>CComPtrBase クラス
このクラスは、メモリの COM ベースのルーチンを使用するスマート ポインター クラスの基盤を提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class CComPtrBase
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 スマート ポインターで参照されるオブジェクトの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComPtrBase:: ~ CComPtrBase](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComPtrBase::Advise](#advise)|間の接続を作成するには、このメソッドを呼び出して、`CComPtrBase`のコネクション ポイントとクライアントのシンクとします。|  
|[CComPtrBase::Attach](#attach)|既存のポインターの所有権を取得するには、このメソッドを呼び出します。|  
|[CComPtrBase::CoCreateInstance](#cocreateinstance)|指定したクラス ID、またはプログラムの ID に関連付けられているクラスのオブジェクトを作成するには、このメソッドを呼び出す|  
|[CComPtrBase::CopyTo](#copyto)|コピーするには、このメソッドを呼び出して、`CComPtrBase`別のポインター変数へのポインター。|  
|[CComPtrBase::Detach](#detach)|ポインターの所有権を解放するには、このメソッドを呼び出します。|  
|[CComPtrBase::IsEqualObject](#isequalobject)|かどうか確認には、このメソッドを呼び出して、指定した**IUnknown**に関連付けられている同じオブジェクトを指す、`CComPtrBase`オブジェクトです。|  
|[CComPtrBase::QueryInterface](#queryinterface)|このメソッドでは、指定したインターフェイスへのポインターを返します。|  
|[CComPtrBase::Release](#release)|インターフェイスを解放するには、このメソッドを呼び出します。|  
|[CComPtrBase::SetSite](#setsite)|サイトを設定するには、このメソッドを呼び出して、`CComPtrBase`オブジェクトを**IUnknown**の親オブジェクトです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CComPtrBase::operator T *](#operator_t_star)|キャスト演算子です。|  
|[CComPtrBase::operator!](#operator_not)|NOT 演算子。|  
|[CComPtrBase::operator >/documents/report1.rdl」の](#operator_amp)|&Gt;/documents/report1.rdl」の演算子です。|  
|[CComPtrBase::operator *](#operator_star)|* 演算子。|  
|[CComPtrBase::operator](#ccomptrbase__operator lt)|小・なり演算子です。|  
|[CComPtrBase::operator = =](#operator_eq_eq)|等値演算子。|  
|[-> CComPtrBase::operator](#operator_ptr)|メンバーへのポインター演算子です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[解放](#p)|ポインターのデータ メンバー変数です。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、COM メモリ管理ルーチンを使用している他のスマート ポインターの基礎[CComQIPtr](../../atl/reference/ccomqiptr-class.md)と[CComPtr](../../atl/reference/ccomptr-class.md)します。 派生クラス コンス トラクターと演算子を追加しますがによって提供されるメソッドに依存して`CComPtrBase`します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcomcli.h  
  
##  <a name="a-nameadvisea--ccomptrbaseadvise"></a><a name="advise"></a>CComPtrBase::Advise  
 間の接続を作成するには、このメソッドを呼び出して、`CComPtrBase`のコネクション ポイントとクライアントのシンクとします。  
  
```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 クライアントへのポインター **IUnknown**します。  
  
 `iid`  
 接続ポイントの GUID です。 通常、これは接続ポイントで管理するアウトゴーイング インターフェイスの場合と同じです。  
  
 `pdw`  
 接続を一意に識別するクッキーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください[AtlAdvise](http://msdn.microsoft.com/library/625a2f03-6b7f-4761-be5d-d2871d1d3254)の詳細。  
  
##  <a name="a-nameattacha--ccomptrbaseattach"></a><a name="attach"></a>CComPtrBase::Attach  
 既存のポインターの所有権を取得するには、このメソッドを呼び出します。  
  
```
void Attach(T* p2) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p2`  
 `CComPtrBase` This ポインターの所有権を持つオブジェクト。  
  
### <a name="remarks"></a>コメント  
 **アタッチ**呼び出し[CComPtrBase::Release](#release) 、既存の[解放](#p)メンバー変数を示し、代入`p2`に`CComPtrBase::p`します。 ときに、`CComPtrBase`オブジェクトへのポインターの所有権を取得するは自動的に呼び出すことが`Release`にポインターをいずれかを削除するポインターでオブジェクトの参照カウントが 0 になった場合にデータを割り当てます。  
  
##  <a name="a-namedtora--ccomptrbaseccomptrbase"></a><a name="dtor"></a>CComPtrBase:: ~ CComPtrBase  
 デストラクターです。  
  
```
~CComPtrBase() throw();
```  
  
### <a name="remarks"></a>コメント  
 指すインターフェイスを解放`CComPtrBase`します。  
  
##  <a name="a-namecocreateinstancea--ccomptrbasecocreateinstance"></a><a name="cocreateinstance"></a>CComPtrBase::CoCreateInstance  
 指定したクラス ID、またはプログラムの ID に関連付けられているクラスのオブジェクトを作成するには、このメソッドを呼び出す  
  
```
HRESULT CoCreateInstance(  
    LPCOLESTR szProgID,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();

HRESULT CoCreateInstance(  
    REFCLSID rclsid,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `szProgID`  
 ProgID、CLSID を回復するために使用へのポインター。  
  
 `pUnkOuter`  
 場合**NULL**集計の一部として、オブジェクトが作成されていないことを示します。 以外の場合**NULL**、集約オブジェクトへのポインターは、 **IUnknown**インターフェイス (制御**IUnknown**)。  
  
 `dwClsContext`  
 新しく作成されたオブジェクトを管理するコードを実行するコンテキスト。  
  
 `rclsid`  
 CLSID は、データとオブジェクトの作成に使用されるコードに関連付けられています。  
  
### <a name="return-value"></a>戻り値  
 失敗した場合、成功した場合、または REGDB_E_CLASSNOTREG、CLASS_E_NOAGGREGATION、CO_E_CLASSSTRING または E_NOINTERFACE に S_OK を返します。 参照してください[とも](http://msdn.microsoft.com/library/windows/desktop/ms686615)と[この](http://msdn.microsoft.com/library/windows/desktop/ms688386)これらのエラーの詳細についてです。  
  
### <a name="remarks"></a>コメント  
 メソッドの最初のフォームが呼び出されると、[この](http://msdn.microsoft.com/library/windows/desktop/ms688386)CLSID を回復するために使用します。 両方の形式[とも](http://msdn.microsoft.com/library/windows/desktop/ms686615)です。  
  
 デバッグ ビルドで、アサーション エラーが発生場合[解放](#p)が NULL と等しくないです。  
  
##  <a name="a-namecopytoa--ccomptrbasecopyto"></a><a name="copyto"></a>CComPtrBase::CopyTo  
 コピーするには、このメソッドを呼び出して、`CComPtrBase`別のポインター変数へのポインター。  
  
```
HRESULT CopyTo(T** ppT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *ppT*  
 受け取る変数のアドレス、`CComPtrBase`ポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、正常に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 コピー、`CComPtrBase`へのポインター *ppT*します。 参照カウント、[解放](#p)メンバー変数が増加します。  
  
 場合に返される HRESULT エラー *ppT*が NULL です。 デバッグ ビルドで、アサーション エラーが発生場合*ppT*が NULL です。  
  
##  <a name="a-namedetacha--ccomptrbasedetach"></a><a name="detach"></a>CComPtrBase::Detach  
 ポインターの所有権を解放するには、このメソッドを呼び出します。  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ポインターのコピーを返します。  
  
### <a name="remarks"></a>コメント  
 ポインターの所有権を解放、[解放](#p)データ メンバー変数を NULL にし、ポインターのコピーを返します。  
  
##  <a name="a-nameisequalobjecta--ccomptrbaseisequalobject"></a><a name="isequalobject"></a>CComPtrBase::IsEqualObject  
 かどうか確認には、このメソッドを呼び出して、指定した**IUnknown**に関連付けられている同じオブジェクトを指す、`CComPtrBase`オブジェクトです。  
  
```
bool IsEqualObject(IUnknown* pOther) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pOther`  
 **IUnknown \* **を比較します。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトは同一では false をそれ以外の場合がある場合に true を返します。  
  
##  <a name="a-nameoperatornota--ccomptrbaseoperator-"></a><a name="operator_not"></a>CComPtrBase::operator!  
 NOT 演算子。  
  
```
bool operator!() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 場合は true を返します。、`CComHeapPtr`ポインターが NULL、false それ以外の場合。  
  
##  <a name="a-nameoperatorampa--ccomptrbaseoperator-amp"></a><a name="operator_amp"></a>CComPtrBase::operator&amp;  
 &Gt;/documents/report1.rdl」の演算子です。  
  
```
T** operator&() throw();
```  
  
### <a name="return-value"></a>戻り値  
 によって指されるオブジェクトのアドレスを返す、`CComPtrBase`オブジェクトです。  
  
##  <a name="a-nameoperatorstara--ccomptrbaseoperator-"></a><a name="operator_star"></a>CComPtrBase::operator *  
 * 演算子。  
  
```
T& operator*() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 値を返します[解放](#p); によって参照されるオブジェクトへのポインターは、`CComPtrBase`オブジェクトです。  
  
 場合に、アサーション エラーが発生する場合はデバッグ ビルドで、[解放](#p)が NULL と等しくないです。  
  
##  <a name="a-nameoperatoreqeqa--ccomptrbaseoperator-"></a><a name="operator_eq_eq"></a>CComPtrBase::operator = =  
 等値演算子。  
  
```
bool operator== (T* pT) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pT*  
 オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 場合は true を返します。`CComPtrBase`と*pT*オブジェクトを指す同じ、false それ以外の場合。  
  
##  <a name="a-nameoperatorptra--ccomptrbaseoperator--gt"></a><a name="operator_ptr"></a>CComPtrBase::operator-&gt;  

 メンバーへのポインター演算子です。  
  
```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 値を返す、[解放](#p)データ メンバー変数です。  
  
### <a name="remarks"></a>コメント  
 この演算子が指すクラスのメソッドを呼び出すを使用して、`CComPtrBase`オブジェクトです。 デバッグ ビルドで、アサーション エラーが発生場合、`CComPtrBase`データ メンバーが NULL を指します。  
  
##  <a name="a-nameoperatorlta--ccomptrbaseoperator-lt"></a><a name="operator_lt"></a>CComPtrBase::operator&lt;  
 小・なり演算子です。  
  
```
bool operator<(T* pT) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pT*  
 オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ポインターは、現在のオブジェクトによって管理されている場合は true を返しますでは、比較するポインターより小さいです。  
  
##  <a name="a-nameoperatortstara--ccomptrbaseoperator-t"></a><a name="operator_t_star"></a>CComPtrBase::operator T *  
 キャスト演算子です。  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>コメント  
 クラス テンプレートで定義されたオブジェクト データ型へのポインターを返します。  
  
##  <a name="a-namepa--ccomptrbasep"></a><a name="p"></a>解放  
 ポインターのデータ メンバー変数です。  
  
```
T* p;
```  
  
### <a name="remarks"></a>コメント  
 このメンバー変数は、ポインターの情報を保持します。  
  
##  <a name="a-namequeryinterfacea--ccomptrbasequeryinterface"></a><a name="queryinterface"></a>CComPtrBase::QueryInterface  
 このメソッドでは、指定したインターフェイスへのポインターを返します。  
  
```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `Q`  
 あるインターフェイス ポインターが必要なオブジェクトの型。  
  
 `pp`  
 要求されたインターフェイス ポインターを受け取る出力変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 失敗した場合、成功した場合、または E_NOINTERFACE に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す[:queryinterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)します。  
  
 デバッグ ビルドで、アサーション エラーが発生場合*pp*が NULL と等しくないです。  
  
##  <a name="a-namereleasea--ccomptrbaserelease"></a><a name="release"></a>CComPtrBase::Release  
 インターフェイスを解放するには、このメソッドを呼び出します。  
  
```
void Release() throw();
```  
  
### <a name="remarks"></a>コメント  
 インターフェイスが解放されると、および[解放](#p)は NULL に設定します。  
  
##  <a name="a-namesetsitea--ccomptrbasesetsite"></a><a name="setsite"></a>CComPtrBase::SetSite  
 サイトを設定するには、このメソッドを呼び出して、`CComPtrBase`オブジェクトを**IUnknown**の親オブジェクトです。  
  
```
HRESULT SetSite(IUnknown* punkParent) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `punkParent`  
 ポインター、 **IUnknown**親のインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す[AtlSetChildSite](http://msdn.microsoft.com/library/2a8ece19-6bfd-4e89-9d1d-e5a78f95e2df)します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

