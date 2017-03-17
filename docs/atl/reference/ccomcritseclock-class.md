---
title: "CComCritSecLock クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCritSecLock
- ATLBASE/ATL::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::Lock
- ATLBASE/ATL::CComCritSecLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComCritSecLock class
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
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
ms.openlocfilehash: 71b9ab8b11adc946656c2192c2f0f06555ef1254
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcritseclock-class"></a>CComCritSecLock クラス
このクラスは、ロックおよびクリティカル セクション オブジェクトのロックを解除するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template<class TLock> class CComCritSecLock
```  
  
#### <a name="parameters"></a>パラメーター  
 *TLock*  
 ロックおよびロック解除するオブジェクト。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComCritSecLock::CComCritSecLock](#ctor)|コンストラクターです。|  
|[CComCritSecLock:: ~ CComCritSecLock](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComCritSecLock::Lock](#lock)|クリティカル セクション オブジェクトをロックするには、このメソッドを呼び出します。|  
|[CComCritSecLock::Unlock](#unlock)|クリティカル セクション オブジェクトのロックを解除するには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 このクラスを使用して、ロックおよびでより安全な方法でオブジェクトをロック解除、 [CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)または[CComAutoCriticalSection クラス](../../atl/reference/ccomautocriticalsection-class.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="ctor"></a>CComCritSecLock::CComCritSecLock  
 コンストラクターです。  
  
```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```  
  
### <a name="parameters"></a>パラメーター  
 *cs*  
 クリティカル セクション オブジェクト。  
  
 `bInitialLock`  
 最初のロック状態: **true**がロックされていることを意味します。  
  
### <a name="remarks"></a>コメント  
 クリティカル セクション オブジェクトを初期化します。  
  
##  <a name="dtor"></a>CComCritSecLock:: ~ CComCritSecLock  
 デストラクターです。  
  
```
~CComCritSecLock() throw();
```  
  
### <a name="remarks"></a>コメント  
 クリティカル セクション オブジェクトのロックを解除します。  
  
##  <a name="lock"></a>CComCritSecLock::Lock  
 クリティカル セクション オブジェクトをロックするには、このメソッドを呼び出します。  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが正常にロックされた場合は S_OK またはエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 オブジェクトが既にロックされているデバッグ ビルドで ASSERT エラーが発生します。  
  
##  <a name="unlock"></a>CComCritSecLock::Unlock  
 クリティカル セクション オブジェクトのロックを解除するには、このメソッドを呼び出します。  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトは、既にロックされているが、デバッグ ビルドで ASSERT エラーが発生します。  
  
## <a name="see-also"></a>関連項目  
 [CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)   
 [CComAutoCriticalSection クラス](../../atl/reference/ccomautocriticalsection-class.md)

