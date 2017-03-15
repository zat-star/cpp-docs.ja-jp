---
title: "CComApartment クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComApartment
- CComApartment
- ATL.CComApartment
dev_langs:
- C++
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
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
translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 9359e2ab8c4a84ab66441e3eb8cfd39520fd4e8d
ms.lasthandoff: 02/24/2017

---
# <a name="ccomapartment-class"></a>CComApartment クラス
このクラスは、アパートメント スレッド プールの EXE モジュールでの管理サポートを提供します。  
  
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
|[CComApartment::m_hThread](#m_hthread)|スレッドへのハンドルが含まれています。|  
|[CComApartment::m_nLockCnt](#m_nlockcnt)|スレッドの現在のロック カウントが含まれています。|  
  
## <a name="remarks"></a>コメント  
 `CComApartment`によって使用される[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)アパートメント スレッド プールの EXE モジュールを管理します。 `CComApartment`スレッドのカウントがインクリメントおよびデクリメント、ロックするためのメソッドを提供します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="a-nameapartmenta--ccomapartmentapartment"></a><a name="apartment"></a>CComApartment::Apartment  
 スレッドの開始アドレスをマークします。  
  
```
DWORD Apartment();
```  
  
### <a name="return-value"></a>戻り値  
 常に 0 です。  
  
### <a name="remarks"></a>コメント  
 自動的に設定[CComAutoThreadModule::Init](../../atl/reference/ccomautothreadmodule-class.md#init)します。  
  
##  <a name="a-nameccomapartmenta--ccomapartmentccomapartment"></a><a name="ccomapartment"></a>CComApartment::CComApartment  
 コンストラクターです。  
  
```
CComApartment();
```  
  
### <a name="remarks"></a>コメント  
 初期化、`CComApartment`データ メンバー [m_nLockCnt](#m_nlockcnt)と[で](#m_hthread)します。  
  
##  <a name="a-namegetlockcounta--ccomapartmentgetlockcount"></a><a name="getlockcount"></a>CComApartment::GetLockCount  
 スレッドの現在のロック カウントを返します。  
  
```
LONG GetLockCount();
```  
  
### <a name="return-value"></a>戻り値  
 スレッドのロック カウントします。  
  
##  <a name="a-namelocka--ccomapartmentlock"></a><a name="lock"></a>CComApartment::Lock  
 スレッドのロック カウントをインクリメントします。  
  
```
LONG Lock();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役に立たないかテスト可能性のある値。  
  
### <a name="remarks"></a>コメント  
 によって呼び出される[CComAutoThreadModule::Lock](../../atl/reference/ccomautothreadmodule-class.md#lock)します。  
  
 スレッドのロック カウントは、統計目的のために使用されます。  
  
##  <a name="a-namemdwthreadida--ccomapartmentmdwthreadid"></a><a name="m_dwthreadid"></a>CComApartment::m_dwThreadID  
 スレッドの識別子が含まれています。  
  
```
DWORD m_dwThreadID;
```  
  
##  <a name="a-namemhthreada--ccomapartmentmhthread"></a><a name="m_hthread"></a>CComApartment::m_hThread  
 スレッドへのハンドルが含まれています。  
  
```
HANDLE m_hThread;
```  
  
##  <a name="a-namemnlockcnta--ccomapartmentmnlockcnt"></a><a name="m_nlockcnt"></a>CComApartment::m_nLockCnt  
 スレッドの現在のロック カウントが含まれています。  
  
```
LONG m_nLockCnt;
```  
  
##  <a name="a-nameunlocka--ccomapartmentunlock"></a><a name="unlock"></a>CComApartment::Unlock  
 スレッドのロック カウントをデクリメントします。  
  
```
LONG Unlock();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役に立たないかテスト可能性のある値。  
  
### <a name="remarks"></a>コメント  
 によって呼び出される[CComAutoThreadModule::Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock)します。  
  
 スレッドのロック カウントは、統計目的のために使用されます。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

