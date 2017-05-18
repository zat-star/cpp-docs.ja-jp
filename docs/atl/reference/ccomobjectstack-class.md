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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 0738eae13fdca5906596194016ce22812fbfcd36
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectstack-class"></a>CComObjectStack クラス
このクラスは、一時的な COM オブジェクトを作成し、スケルトンの実装を提供**IUnknown**します。  
  
## <a name="syntax"></a>構文  
  
```
template <class  Base>  
class CComObjectStack
 : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 派生したクラスに、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のインターフェイスからも、です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComObjectStack::CComObjectStack](#ccomobjectstack)|コンストラクターです。|  
|[CComObjectStack:: ~ CComObjectStack](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComObjectStack::AddRef](#addref)|0 を返します。 デバッグ モードで`_ASSERTE`します。|  
|[CComObjectStack::QueryInterface](#queryinterface)|返します。 **E_NOINTERFACE**します。 デバッグ モードで`_ASSERTE`します。|  
|[CComObjectStack::Release](#release)|0 を返します。 デバッグ モードで`_ASSERTE`します。 ~|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComObjectStack::m_hResFinalConstruct](#m_hresfinalconstruct)|含む、 **HRESULT**の構築時に返される、`CComObjectStack`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `CComObjectStack`一時的な COM オブジェクトを作成し、オブジェクトのスケルトンの実装を提供するために使用**IUnknown**します。 通常、オブジェクトは、1 つの関数をスタックにプッシュされます) 内のローカル変数として使用されます。 関数が終了するときに、オブジェクトが破棄されるため、効率を向上させる参照カウントが実行されませんが。  
  
 次の例では、関数内で使用される COM オブジェクトを作成する方法を示します。  
  
 [!code-cpp[NVC_ATL_COM&#42;](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]  
  
 一時オブジェクト`Tempobj`がスタックにプッシュされ、自動的には、関数が終了したときに表示されなくなります。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Base`  
  
 `CComObjectStack`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="addref"></a>CComObjectStack::AddRef  
 0 を返します。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 0 を返します。  
  
### <a name="remarks"></a>コメント  
 デバッグ モードで`_ASSERTE`します。  
  
##  <a name="ccomobjectstack"></a>CComObjectStack::CComObjectStack  
 コンストラクターです。  
  
```
CComObjectStack(void* = NULL);
```  
  
### <a name="remarks"></a>コメント  
 呼び出し`FinalConstruct`し、設定[m_hResFinalConstruct](#m_hresfinalconstruct)に、`HRESULT`によって返される`FinalConstruct`です。 基本クラスを派生していない場合[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)、独自に指定する必要があります`FinalConstruct`メソッドです。 このデストラクターは `FinalRelease` を呼び出します。  
  
##  <a name="dtor"></a>CComObjectStack:: ~ CComObjectStack  
 デストラクターです。  
  
```
CComObjectStack();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放[FinalRelease](ccomobjectrootex-class.md#finalrelease)します。  
  
##  <a name="m_hresfinalconstruct"></a>CComObjectStack::m_hResFinalConstruct  
 含む、`HRESULT`呼び出しで返される`FinalConstruct`の構築中に、`CComObjectStack`オブジェクトです。  
  
```
HRESULT    m_hResFinalConstruct;
```  
  
##  <a name="queryinterface"></a>CComObjectStack::QueryInterface  
 返します。 **E_NOINTERFACE**します。  
  
```
HRESULT    QueryInterface(REFIID, void**)
 ;
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **E_NOINTERFACE**します。  
  
### <a name="remarks"></a>コメント  
 デバッグ モードで`_ASSERTE`します。  
  
##  <a name="release"></a>CComObjectStack::Release  
 0 を返します。  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>戻り値  
 0 を返します。  
  
### <a name="remarks"></a>コメント  
 デバッグ モードで`_ASSERTE`します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../atl/reference/ccomaggobject-class.md)   
 [クラス](../../atl/reference/ccomobject-class.md)   
 [CComObjectGlobal クラス](../../atl/reference/ccomobjectglobal-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

