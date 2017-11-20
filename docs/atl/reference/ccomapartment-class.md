---
title: "CComApartment クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComApartment
- ATLBASE/ATL::CComApartment
- ATLBASE/ATL::CComApartment::CComApartment
- ATLBASE/ATL::CComApartment::Apartment
- ATLBASE/ATL::CComApartment::GetLockCount
- ATLBASE/ATL::CComApartment::Lock
- ATLBASE/ATL::CComApartment::Unlock
- ATLBASE/ATL::CComApartment::m_dwThreadID
- ATLBASE/ATL::CComApartment::m_hThread
- ATLBASE/ATL::CComApartment::m_nLockCnt
dev_langs: C++
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0a7e7fce463e7aabe6b27cb9e5fb3dbb36fd8983
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ccomapartment-class"></a>CComApartment クラス
このクラスは、アパートメント スレッド プールの EXE モジュールでの管理のサポートを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CComApartment
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComApartment::CComApartment](#ccomapartment)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComApartment::Apartment](#apartment)|スレッドの開始アドレスをマークします。|  
|[CComApartment::GetLockCount](#getlockcount)|スレッドの現在のロック カウントを返します。|  
|[CComApartment::Lock](#lock)|スレッドのロック カウントをインクリメントします。|  
|[CComApartment::Unlock](#unlock)|スレッドのロック カウントをデクリメントします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComApartment::m_dwThreadID](#m_dwthreadid)|スレッドの識別子が含まれています。|  
|[CComApartment::m_hThread](#m_hthread)|スレッドのハンドルが含まれています。|  
|[CComApartment::m_nLockCnt](#m_nlockcnt)|スレッドの現在のロック カウントを格納します。|  
  
## <a name="remarks"></a>コメント  
 `CComApartment`によって使用される[は](../../atl/reference/ccomautothreadmodule-class.md)アパートメント スレッド プールの EXE モジュールを管理します。 `CComApartment`インクリメントおよびデクリメント、ロックのメソッドは、スレッドでカウントを提供します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="apartment"></a>CComApartment::Apartment  
 スレッドの開始アドレスをマークします。  
  
```
DWORD Apartment();
```  
  
### <a name="return-value"></a>戻り値  
 常に 0 です。  
  
### <a name="remarks"></a>コメント  
 中に自動的に設定[CComAutoThreadModule::Init](../../atl/reference/ccomautothreadmodule-class.md#init)です。  
  
##  <a name="ccomapartment"></a>CComApartment::CComApartment  
 コンストラクターです。  
  
```
CComApartment();
```  
  
### <a name="remarks"></a>コメント  
 初期化、`CComApartment`データ メンバー [m_nLockCnt](#m_nlockcnt)と[で](#m_hthread)です。  
  
##  <a name="getlockcount"></a>CComApartment::GetLockCount  
 スレッドの現在のロック カウントを返します。  
  
```
LONG GetLockCount();
```  
  
### <a name="return-value"></a>戻り値  
 スレッドのロック カウントします。  
  
##  <a name="lock"></a>CComApartment::Lock  
 スレッドのロック カウントをインクリメントします。  
  
```
LONG Lock();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役に立たず、テスト可能な値です。  
  
### <a name="remarks"></a>コメント  
 によって呼び出されます[CComAutoThreadModule::Lock](../../atl/reference/ccomautothreadmodule-class.md#lock)です。  
  
 スレッドのロック カウントは、統計目的のために使用されます。  
  
##  <a name="m_dwthreadid"></a>CComApartment::m_dwThreadID  
 スレッドの識別子が含まれています。  
  
```
DWORD m_dwThreadID;
```  
  
##  <a name="m_hthread"></a>CComApartment::m_hThread  
 スレッドのハンドルが含まれています。  
  
```
HANDLE m_hThread;
```  
  
##  <a name="m_nlockcnt"></a>CComApartment::m_nLockCnt  
 スレッドの現在のロック カウントを格納します。  
  
```
LONG m_nLockCnt;
```  
  
##  <a name="unlock"></a>CComApartment::Unlock  
 スレッドのロック カウントをデクリメントします。  
  
```
LONG Unlock();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役に立たず、テスト可能な値です。  
  
### <a name="remarks"></a>コメント  
 によって呼び出されます[CComAutoThreadModule::Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock)です。  
  
 スレッドのロック カウントは、統計目的のために使用されます。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
