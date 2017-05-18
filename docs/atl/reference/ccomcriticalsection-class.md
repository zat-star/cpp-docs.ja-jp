---
title: "CComCriticalSection クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCriticalSection
- ATLCORE/ATL::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::Init
- ATLCORE/ATL::CComCriticalSection::Lock
- ATLCORE/ATL::CComCriticalSection::Term
- ATLCORE/ATL::CComCriticalSection::Unlock
- ATLCORE/ATL::CComCriticalSection::m_sec
dev_langs:
- C++
helpviewer_keywords:
- CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
caps.latest.revision: 21
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: a7c4fbc87ff06bb09766eb3e4ad0d7c5275eed65
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcriticalsection-class"></a>CComCriticalSection クラス
このクラスは、取得し、クリティカル セクション オブジェクトの所有権を解放するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CComCriticalSection
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComCriticalSection::CComCriticalSection](#ccomcriticalsection)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComCriticalSection::Init](#init)|作成し、クリティカル セクション オブジェクトを初期化します。|  
|[CComCriticalSection::Lock](#lock)|クリティカル セクション オブジェクトの所有権を取得します。|  
|[CComCriticalSection::Term](#term)|クリティカル セクション オブジェクトによって使用されているシステム リソースを解放します。|  
|[CComCriticalSection::Unlock](#unlock)|クリティカル セクション オブジェクトの所有権を解放します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComCriticalSection::m_sec](#m_sec)|A **CRITICAL_SECTION**オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `CComCriticalSection`クラスのような[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)点が明示的に初期化し、クリティカル セクションを解放する必要があります。  
  
 通常、使用して`CComCriticalSection`を通じて、`typedef`名[CriticalSection](ccommultithreadmodel-class.md#criticalsection)します。 この名前を参照して`CComCriticalSection`と[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)が使用されています。  

  
 参照してください[CComCritSecLock クラス](../../atl/reference/ccomcritseclock-class.md)呼び出しよりもこのクラスを使用するより安全な方法を`Lock`と`Unlock`直接します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
##  <a name="ccomcriticalsection"></a>CComCriticalSection::CComCriticalSection  
 コンストラクターです。  
  
```
CComCriticalSection() throw();
```  
  
### <a name="remarks"></a>コメント  
 セット、 [m_sec](#m_sec)データ メンバーを NULL に**します。**  
  
##  <a name="init"></a>CComCriticalSection::Init  
 Win32 関数を呼び出す[InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472)に格納されている、クリティカル セクション オブジェクトを初期化しますが、 [m_sec](#m_sec)データ メンバーです。  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`成功した場合、 **E_OUTOFMEMORY**または**E_FAIL**失敗します。  
  
##  <a name="lock"></a>CComCriticalSection::Lock  
 Win32 関数を呼び出す[EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608)、スレッドがクリティカル セクション オブジェクトに含まれているの所有権を取得するまで待機したどの、 [m_sec](#m_sec)データ メンバーです。  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`成功した場合、 **E_OUTOFMEMORY**または**E_FAIL**失敗します。  
  
### <a name="remarks"></a>コメント  
 呼び出して、クリティカル セクション オブジェクトを初期化まず必要があります、 [Init](#init)メソッドです。 保護されているコードの実行が完了すると、スレッドで呼び出す必要があります[Unlock](#unlock)クリティカル セクションの所有権を解放します。  
  
##  <a name="m_sec"></a>CComCriticalSection::m_sec  
 クリティカル セクション オブジェクトすべてで使用を含む`CComCriticalSection`メソッドです。  
  
```
CRITICAL_SECTION m_sec;
```  
  
##  <a name="term"></a>CComCriticalSection::Term  
 Win32 関数を呼び出す[DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552)に含まれているクリティカル セクション オブジェクトによって使用されているすべてのリソースを解放、 [m_sec](#m_sec)データ メンバーです。  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 1 回`Term`が呼び出された、重要なセクションは、同期には使用できなくします。  
  
##  <a name="unlock"></a>CComCriticalSection::Unlock  
 Win32 関数を呼び出す[により](http://msdn.microsoft.com/library/windows/desktop/ms684169)に含まれているクリティカル セクション オブジェクトの所有権を解放する、 [m_sec](#m_sec)データ メンバーです。  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 所有権を取得するスレッドを呼び出す必要があります、[ロック](#lock)メソッドです。 各呼び出し`Lock`に対応する呼び出しを必要と`Unlock`クリティカル セクションの所有権を解放します。  
  
## <a name="see-also"></a>関連項目  
 [CComFakeCriticalSection クラス](../../atl/reference/ccomfakecriticalsection-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComCritSecLock クラス](../../atl/reference/ccomcritseclock-class.md)

