---
title: "CComObjectNoLock クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::AddRef
- ATLCOM/ATL::CComObjectNoLock::QueryInterface
- ATLCOM/ATL::CComObjectNoLock::Release
dev_langs:
- C++
helpviewer_keywords:
- CComObjectNoLock class
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
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
ms.openlocfilehash: 4cf4cad1a3b1a4ac0a21ef76a0eaca35732abf3a
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectnolock-class"></a>CComObjectNoLock クラス
このクラスは実装**IUnknown**の非集約オブジェクトですがモジュールのロック数をコンス トラクターでインクリメントされません。  
  
## <a name="syntax"></a>構文  
  
```
template<class Base>  
class CComObjectNoLock : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 派生したクラスに、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のインターフェイスからも、です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|コンストラクターです。|  
|[CComObjectNoLock:: ~ CComObjectNoLock](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComObjectNoLock::AddRef](#addref)|オブジェクトの参照カウントをインクリメントします。|  
|[CComObjectNoLock::QueryInterface](#queryinterface)|要求されたインターフェイスへのポインターを返します。|  
|[CComObjectNoLock::Release](#release)|オブジェクトの参照カウントをデクリメントします。|  
  
## <a name="remarks"></a>コメント  
 `CComObjectNoLock`に似ていますが[と](../../atl/reference/ccomobject-class.md)を実装しているという点で[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)非集約オブジェクトです。 ただし、`CComObjectNoLock`増分値はモジュールのロックは、コンス トラクター内でカウントされます。  
  
 ATL では、`CComObjectNoLock`のクラス ファクトリを内部的にします。 一般に、このクラスを直接使用するがありません。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Base`  
  
 `CComObjectNoLock`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="addref"></a>CComObjectNoLock::AddRef  
 オブジェクトの参照カウントをインクリメントします。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役に立たないかテスト可能性のある値。  
  
##  <a name="ccomobjectnolock"></a>CComObjectNoLock::CComObjectNoLock  
 コンストラクターです。 異なり[と](../../atl/reference/ccomobject-class.md)モジュールのロック カウントをインクリメントしません。  
  
```
CComObjectNoLock(void* = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 **void\***  
 [in]この名前のないパラメーターは使用されません。 他の対称性が存在する**ほか***XXX*`Object`*XXX*コンス トラクターです。  
  
##  <a name="dtor"></a>CComObjectNoLock:: ~ CComObjectNoLock  
 デストラクターです。  
  
```
~CComObjectNoLock();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放[FinalRelease](ccomobjectrootex-class.md#finalrelease)します。  

  
##  <a name="queryinterface"></a>CComObjectNoLock::QueryInterface  
 要求されたインターフェイスへのポインターを取得します。  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]要求されているインターフェイスの識別子。  
  
 `ppvObject`  
 [out]によって識別されるインターフェイス ポインターへのポインター`iid`します。 オブジェクトがこのインターフェイスをサポートしていない場合`ppvObject`に設定されている**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="release"></a>CComObjectNoLock::Release  
 オブジェクトの参照カウントをデクリメントします。  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>戻り値  
 デバッグ ビルドで、**リリース**診断に役に立たないかテスト可能性のある値を返します。 非デバッグ ビルドでは、**リリース**常に 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

