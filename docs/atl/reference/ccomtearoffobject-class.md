---
title: "CComTearOffObject クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
dev_langs:
- C++
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 3e8e997f26df1adca8050bd4d967a38297685831
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ccomtearoffobject-class"></a>CComTearOffObject クラス
このクラスは、ティアオフ インターフェイスを実装します。  
  
## <a name="syntax"></a>構文  
  
```
template<class Base>
class CComTearOffObject : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 ティアオフ クラスから派生`CComTearOffObjectBase`ティアオフ オブジェクトをサポートする場合、インターフェイスです。  
  
 ATL は、2 つのフェーズでそのティアオフ インターフェイスを実装する —、`CComTearOffObjectBase`メソッドは、参照カウントを処理し、 `QueryInterface`、中に`CComTearOffObject`を実装[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComTearOffObject::CComTearOffObject](#ccomtearoffobject)|コンストラクターです。|  
|[CComTearOffObject:: ~ CComTearOffObject](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComTearOffObject::AddRef](#addref)|参照カウントをインクリメントする`CComTearOffObject`オブジェクトです。|  
|[CComTearOffObject::QueryInterface](#queryinterface)|ティアオフ クラスまたは所有者クラスのいずれかで要求されたインターフェイスへのポインターを返します。|  
|[CComTearOffObject::Release](#release)|参照カウントをデクリメント、`CComTearOffObject`オブジェクトを破棄します。|  
  
### <a name="ccomtearoffobjectbase-methods"></a>ティアオフ メソッド  
  
|||  
|-|-|  
|[ティアオフ](#ccomtearoffobjectbase)|コンストラクターです。|  
  
### <a name="ccomtearoffobjectbase-data-members"></a>ティアオフ データ メンバー  
  
|||  
|-|-|  
|[m_pOwner](#m_powner)|ポインター、`CComObject`所有者クラスから派生します。|  
  
## <a name="remarks"></a>コメント  
 `CComTearOffObject`そのインターフェイスが照会されたときにのみインスタンス化される個別のオブジェクトとしてティアオフ インターフェイスを実装します。 参照カウントがゼロになると、ティアオフは削除されます。 通常、使用頻度は、主要なオブジェクトのすべてのインスタンスで vtable ポインター ティアオフを使用して保存されるため、インターフェイスのためのティアオフ インターフェイスを作成します。  
  
 ティアオフから実装するクラスを派生させる必要があります`CComTearOffObjectBase`し、どのインターフェイスをサポートする、ティアオフ オブジェクトをするからです。 `CComTearOffObjectBase`所有者クラスおよびスレッド モデルでテンプレート化されます。 所有者クラスをティアオフが実装されているオブジェクトのクラスです。 スレッド モデルを指定しない場合は、既定のスレッド モデルが使用されます。  
  
 ティアオフ クラスを COM マップを作成してください。 ATL は、ティアオフをインスタンス化と、が作成されます**CComTearOffObject\<CYourTearOffClass >**または**ティアオフ\<CYourTearOffClass >**します。  
  
 たとえば、サンプルでは、BEEPER、`CBeeper2`クラスは、ティアオフ クラスおよび`CBeeper`クラスは、所有者クラス。  
  
 [!code-cpp[NVC_ATL_COM&#43;](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Base`  
  
 `CComTearOffObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="addref"></a>CComTearOffObject::AddRef  
 参照カウントをインクリメント、`CComTearOffObject`を&1; つのオブジェクト。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役立ちますしテスト可能性のある値。  
  
##  <a name="ccomtearoffobject"></a>CComTearOffObject::CComTearOffObject  
 コンストラクターです。  
  
```
CComTearOffObject(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 [in]ポインターへのポインターに変換されますが、**と\<所有者 >**オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 いずれかで所有者の参照カウントをインクリメントします。  
  
##  <a name="dtor"></a>CComTearOffObject:: ~ CComTearOffObject  
 デストラクターです。  
  
```
~CComTearOffObject();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放、モジュールをデクリメントし、FinalRelease を呼び出してロック カウントします。  
  
##  <a name="ccomtearoffobjectbase"></a>CComTearOffObject::CComTearOffObjectBase  
 コンストラクターです。  
  
```
CComTearOffObjectBase();
```  
  
### <a name="remarks"></a>コメント  
 初期化、 [m_pOwner](#m_powner)メンバー **NULL**します。  
  
##  <a name="m_powner"></a>CComTearOffObject::m_pOwner  
 ポインター、[と](../../atl/reference/ccomobject-class.md)から派生したオブジェクト*所有者*します。  
  
```
CComObject<Owner>* m_pOwner;
```  
  
### <a name="parameters"></a>パラメーター  
 *所有者*  
 [in]実装するクラスをティアオフです。  
  
### <a name="remarks"></a>コメント  
 ポインターを初期化**NULL**の構築時にします。  
  
##  <a name="queryinterface"></a>CComTearOffObject::QueryInterface  
 要求されたインターフェイスへのポインターを取得します。  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]要求されているインターフェイスの IID です。  
  
 `ppvObject`  
 [out]によって識別されるインターフェイス ポインターへのポインター `iid`、または**NULL**インターフェイスが見つからない場合。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 まず、ティアオフ クラス上のインターフェイスを照会します。 インターフェイスがない場合、所有者オブジェクトのインターフェイスを照会します。 要求されたインターフェイスの場合**IUnknown**、返します、 **IUnknown**所有者のです。  
  
##  <a name="release"></a>CComTearOffObject::Release  
 参照カウントが&1; つデクリメントし、参照カウントが&0; の場合は、削除、`CComTearOffObject`です。  
  
```
STDMETHOD_ULONG Release();
```  
  
### <a name="return-value"></a>戻り値  
 非デバッグ ビルドでは、常に&0; を返します。 デバッグ ビルドで、診断に役に立たないかテスト可能性のある値を返します。  
  
## <a name="see-also"></a>関連項目  
 [ティアオフ クラス](../../atl/reference/ccomcachedtearoffobject-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

