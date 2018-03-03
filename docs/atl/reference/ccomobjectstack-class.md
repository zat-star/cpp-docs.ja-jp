---
title: "CComObjectStack クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectStack
- ATLCOM/ATL::CComObjectStack
- ATLCOM/ATL::CComObjectStack::CComObjectStack
- ATLCOM/ATL::CComObjectStack::AddRef
- ATLCOM/ATL::CComObjectStack::QueryInterface
- ATLCOM/ATL::CComObjectStack::Release
- ATLCOM/ATL::CComObjectStack::m_hResFinalConstruct
dev_langs:
- C++
helpviewer_keywords:
- CComObjectStack class
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1b7fa9d14a27277d4c26fc6e7589400e19ef1395
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ccomobjectstack-class"></a>CComObjectStack クラス
このクラスは、一時的な COM オブジェクトを作成しのスケルトンの実装を提供**IUnknown**です。  
  
## <a name="syntax"></a>構文  
  
```
template <class  Base>  
class CComObjectStack
 : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 派生したクラス、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のインターフェイスからも、します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComObjectStack::CComObjectStack](#ccomobjectstack)|コンストラクターです。|  
|[CComObjectStack:: ~ CComObjectStack](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComObjectStack::AddRef](#addref)|0 を返します。 デバッグ モードで呼び出す`_ASSERTE`です。|  
|[CComObjectStack::QueryInterface](#queryinterface)|返します**E_NOINTERFACE**です。 デバッグ モードで呼び出す`_ASSERTE`です。|  
|[CComObjectStack::Release](#release)|0 を返します。 デバッグ モードで呼び出す`_ASSERTE`です。 ~|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComObjectStack::m_hResFinalConstruct](#m_hresfinalconstruct)|含まれています、 **HRESULT**の構築時に返される、`CComObjectStack`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `CComObjectStack`一時的な COM オブジェクトを作成し、オブジェクトのスケルトンの実装を提供するために使用**IUnknown**です。 通常、オブジェクトは、1 つの関数は、スタックにプッシュ) 内のローカル変数として使用されます。 以降、オブジェクトが破棄されるは、関数が終了すると、参照カウントは効率を上げるため実行されません。  
  
 次の例では、関数内で使用する COM オブジェクトを作成する方法を示します。  
  
 [!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]  
  
 一時オブジェクト`Tempobj`をスタックにプッシュされ、自動的には、関数が終了したときに表示されなくなります。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Base`  
  
 `CComObjectStack`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcom.h  
  
##  <a name="addref"></a>CComObjectStack::AddRef  
 0 を返します。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 0 を返します。  
  
### <a name="remarks"></a>コメント  
 デバッグ モードで呼び出す`_ASSERTE`です。  
  
##  <a name="ccomobjectstack"></a>CComObjectStack::CComObjectStack  
 コンストラクターです。  
  
```
CComObjectStack(void* = NULL);
```  
  
### <a name="remarks"></a>コメント  
 呼び出し`FinalConstruct`し、設定[m_hResFinalConstruct](#m_hresfinalconstruct)を`HRESULT`によって返される`FinalConstruct`です。 基本クラスを派生していない場合[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)、独自に指定する必要があります`FinalConstruct`メソッドです。 このデストラクターは `FinalRelease` を呼び出します。  
  
##  <a name="dtor"></a>CComObjectStack:: ~ CComObjectStack  
 デストラクターです。  
  
```
CComObjectStack();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放[FinalRelease](ccomobjectrootex-class.md#finalrelease)です。  
  
##  <a name="m_hresfinalconstruct"></a>CComObjectStack::m_hResFinalConstruct  
 含まれています、`HRESULT`呼び出しで返される`FinalConstruct`の構築中に、`CComObjectStack`オブジェクト。  
  
```
HRESULT    m_hResFinalConstruct;
```  
  
##  <a name="queryinterface"></a>CComObjectStack::QueryInterface  
 返します**E_NOINTERFACE**です。  
  
```
HRESULT    QueryInterface(REFIID, void**)
 ;
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOINTERFACE**です。  
  
### <a name="remarks"></a>コメント  
 デバッグ モードで呼び出す`_ASSERTE`です。  
  
##  <a name="release"></a>CComObjectStack::Release  
 0 を返します。  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>戻り値  
 0 を返します。  
  
### <a name="remarks"></a>コメント  
 デバッグ モードで呼び出す`_ASSERTE`です。  
  
## <a name="see-also"></a>参照  
 [クラス](../../atl/reference/ccomaggobject-class.md)   
 [CComObject クラス](../../atl/reference/ccomobject-class.md)   
 [CComObjectGlobal クラス](../../atl/reference/ccomobjectglobal-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
