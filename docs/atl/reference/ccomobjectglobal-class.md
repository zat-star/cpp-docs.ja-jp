---
title: "CComObjectGlobal クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::AddRef
- ATLCOM/ATL::CComObjectGlobal::QueryInterface
- ATLCOM/ATL::CComObjectGlobal::Release
- ATLCOM/ATL::CComObjectGlobal::m_hResFinalConstruct
dev_langs:
- C++
helpviewer_keywords:
- CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 8c371eee9de660a2bb08e67f35a5a6c81d32eee0
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectglobal-class"></a>CComObjectGlobal クラス
このクラスは参照カウントを含むモジュールを管理、`Base`オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```
template<class Base>
class CComObjectGlobal : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 派生したクラスに、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のインターフェイスからも、です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComObjectGlobal::CComObjectGlobal](#ccomobjectglobal)|コンストラクターです。|  
|[CComObjectGlobal:: ~ CComObjectGlobal](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComObjectGlobal::AddRef](#addref)|グローバル カタログ サーバーを実装して`AddRef`します。|  
|[CComObjectGlobal::QueryInterface](#queryinterface)|グローバル カタログ サーバーを実装して`QueryInterface`します。|  
|[CComObjectGlobal::Release](#release)|グローバル カタログ サーバーを実装して**リリース**します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComObjectGlobal::m_hResFinalConstruct](#m_hresfinalconstruct)|含む、 **HRESULT**の構築時に返される、`CComObjectGlobal`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `CComObjectGlobal`含むモジュールの参照カウントを管理、`Base`オブジェクトです。 `CComObjectGlobal`モジュールが解放されない限り、オブジェクトが削除されないようにします。 オブジェクトは、全体のモジュールの参照カウントがゼロになったときにのみ削除されます。  
  
 たとえばを使用して`CComObjectGlobal`、クラス ファクトリは、すべてのクライアントで共有される共通のグローバル オブジェクトを保持できます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Base`  
  
 `CComObjectGlobal`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="addref"></a>CComObjectGlobal::AddRef  
 1 には、オブジェクトの参照カウントをインクリメントします。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役立ちますしテスト可能性のある値。  
  
### <a name="remarks"></a>コメント  
 既定では、`AddRef`呼び出し**_Module::Lock**ここで、 **_Module**のグローバル インスタンスは、 [CComModule](../../atl/reference/ccommodule-class.md)またはその派生クラスです。  
  
##  <a name="ccomobjectglobal"></a>CComObjectGlobal::CComObjectGlobal  
 コンストラクターです。 呼び出し`FinalConstruct`し、設定[m_hResFinalConstruct](#m_hresfinalconstruct)に、`HRESULT`によって返される`FinalConstruct`です。  
  
```
CComObjectGlobal(void* = NULL));
```  
  
### <a name="remarks"></a>コメント  
 基本クラスを派生していない場合[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)、独自に指定する必要があります`FinalConstruct`メソッドです。 このデストラクターは `FinalRelease` を呼び出します。  
  
##  <a name="dtor"></a>CComObjectGlobal:: ~ CComObjectGlobal  
 デストラクターです。  
  
```
CComObjectGlobal();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放[FinalRelease](ccomobjectrootex-class.md#finalrelease)します。  
  
##  <a name="m_hresfinalconstruct"></a>CComObjectGlobal::m_hResFinalConstruct  
 含む、`HRESULT`呼び出しから`FinalConstruct`の構築中に、`CComObjectGlobal`オブジェクトです。  
  
```
HRESULT m_hResFinalConstruct;
```  
  
##  <a name="queryinterface"></a>CComObjectGlobal::QueryInterface  
 要求されたインターフェイス ポインターへのポインターを取得します。  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]要求されているインターフェイスの GUID です。  
  
 `ppvObject`  
 [out]Iid にリンクで識別されるインターフェイス ポインターへのポインターまたは**NULL**インターフェイスが見つからない場合。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 `QueryInterface` が処理するのは、COM マップ テーブル内のインターフェイスのみです。  
  
##  <a name="release"></a>CComObjectGlobal::Release  
 1 で、オブジェクトの参照カウントをデクリメントします。  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>戻り値  
 デバッグ ビルドで、**リリース**診断に役立ちますやテストに値を返します。 非デバッグ ビルドでは、**リリース**常に 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定では、**リリース**呼び出し**_Module::Unlock**ここで、 **_Module**のグローバル インスタンスは、 [CComModule](../../atl/reference/ccommodule-class.md)またはその派生クラスです。  
  
## <a name="see-also"></a>関連項目  
 [CComObjectStack クラス](../../atl/reference/ccomobjectstack-class.md)   
 [クラス](../../atl/reference/ccomaggobject-class.md)   
 [クラス](../../atl/reference/ccomobject-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

