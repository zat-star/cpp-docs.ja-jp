---
title: "CComSafeDeleteCriticalSection クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSafeDeleteCriticalSection
- ATL::CComSafeDeleteCriticalSection
- ATL.CComSafeDeleteCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComSafeDeleteCriticalSection class
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
caps.latest.revision: 18
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 511627de9d4f6411c508dd78a237cf546e2493de
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsafedeletecriticalsection-class"></a>CComSafeDeleteCriticalSection クラス
このクラスは、取得し、クリティカル セクション オブジェクトの所有権を解放するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection](#ccomsafedeletecriticalsection)|コンストラクターです。|  
|[CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComSafeDeleteCriticalSection::Init](#init)|作成し、クリティカル セクション オブジェクトを初期化します。|  
|[CComSafeDeleteCriticalSection::Lock](#lock)|クリティカル セクション オブジェクトの所有権を取得します。|  
|[CComSafeDeleteCriticalSection::Term](#term)|クリティカル セクション オブジェクトによって使用されているシステム リソースを解放します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_bInitialized](#m_binitialized)|フラグかどうか、内部**CRITICAL_SECTION**オブジェクトが初期化されています。|  
  
## <a name="remarks"></a>コメント  
 `CComSafeDeleteCriticalSection`クラスから派生[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)します。 ただし、`CComSafeDeleteCriticalSection`経由での安全性も強化メカニズムを提供[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)します。  
  
 インスタンス`CComSafeDeleteCriticalSection`がスコープ外になるかが明示的にメモリから削除されると、基になるクリティカル セクション オブジェクトは自動的にクリーンアップ有効である場合。 さらに、 [CComSafeDeleteCriticalSection::Term](#term)基になるクリティカル セクション オブジェクトが割り当てられていないかが既にメモリから解放された場合、メソッドが正常に終了します。  
  
 参照してください[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)詳細については、クリティカル セクションのヘルパー クラスです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComSafeDeleteCriticalSection`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
##  <a name="a-nameccomsafedeletecriticalsectiona--ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="ccomsafedeletecriticalsection"></a>CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection  
 コンストラクターです。  
  
```
CComSafeDeleteCriticalSection();
```  
  
### <a name="remarks"></a>コメント  
 セット、 [m_bInitialized](#m_binitialized)データ メンバーを**false**します。  
  
##  <a name="a-namedtora--ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="dtor"></a>CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection  
 デストラクターです。  
  
```
~CComSafeDeleteCriticalSection() throw();
```  
  
### <a name="remarks"></a>コメント  
 内部解放**CRITICAL_SECTION**メモリからオブジェクトの場合、 [m_bInitialized](#m_binitialized)データ メンバーに設定されている**true**します。  
  
##  <a name="a-nameinita--ccomsafedeletecriticalsectioninit"></a><a name="init"></a>CComSafeDeleteCriticalSection::Init  
 基本クラス実装を呼び出して[Init](/visualstudio/debugger/init)設定と[m_bInitialized](#m_binitialized)に**true**正常終了した場合。  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>戻り値  
 結果を返す[CComCriticalSection::Init](../../atl/reference/ccomcriticalsection-class.md#init)します。  
  
##  <a name="a-namelocka--ccomsafedeletecriticalsectionlock"></a><a name="lock"></a>CComSafeDeleteCriticalSection::Lock  
基本クラス実装を呼び出して[ロック](ccomcriticalsection-class.md#lock)します。  

  
```
HRESULT Lock();
```  
  
### <a name="return-value"></a>戻り値  
 結果を返す[CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock)します。  
  
### <a name="remarks"></a>コメント  
 この方法では、 [m_bInitialized](#m_binitialized)データ メンバーに設定されている**true**の入力時です。 この条件が満たされていない場合、デバッグ ビルドでアサーションが生成されます。  
  
 関数の動作の詳細についてを参照してください[CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock)します。  
  
##  <a name="a-namembinitializeda--ccomsafedeletecriticalsectionmbinitialized"></a><a name="m_binitialized"></a>CComSafeDeleteCriticalSection::m_bInitialized  
 フラグかどうか、内部**CRITICAL_SECTION**オブジェクトが初期化されています。  
  
```
bool m_bInitialized;
```  
  
### <a name="remarks"></a>コメント  
 **M_bInitialized**データ メンバーが、基になるの有効性を追跡するために使用される**CRITICAL_SECTION**オブジェクトに関連付けられている、 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)クラスです。 基になる**CRITICAL_SECTION**オブジェクトは、このフラグに設定されていない場合、メモリから解放するのには試行されません**true**します。  
  
##  <a name="a-nameterma--ccomsafedeletecriticalsectionterm"></a><a name="term"></a>CComSafeDeleteCriticalSection::Term  
 基本クラス実装を呼び出して[CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term)場合は、内部**CRITICAL_SECTION**オブジェクトが無効です。  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>戻り値  
 結果を返す[CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term)、または**S_OK**場合[m_bInitialized](#m_binitialized)に設定されている**false**の入力時です。  
  
### <a name="remarks"></a>コメント  
 内部いてもこのメソッドを呼び出しても安全である**CRITICAL_SECTION**オブジェクトが無効です。 場合に、このクラスのデストラクターがこのメソッドを呼び出して、 [m_bInitialized](#m_binitialized)データ メンバーに設定されている**true**します。  
  
## <a name="see-also"></a>関連項目  
 [CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

