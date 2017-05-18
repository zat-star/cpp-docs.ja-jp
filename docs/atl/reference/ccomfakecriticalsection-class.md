---
title: "CComFakeCriticalSection クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 2c1269288e03a8ac9f359dad9acf1a81ddbc84c2
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ccomfakecriticalsection-class"></a>CComFakeCriticalSection クラス
このクラスと同じメソッドを提供する[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)クリティカル セクションは提供されません。  
  
## <a name="syntax"></a>構文  
  
```
class CComFakeCriticalSection
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComFakeCriticalSection::Init](#init)|クリティカル セクションがないので実行されません。|  
|[CComFakeCriticalSection::Lock](#lock)|クリティカル セクションがないので実行されません。|  
|[CComFakeCriticalSection::Term](#term)|クリティカル セクションがないので実行されません。|  
|[CComFakeCriticalSection::Unlock](#unlock)|クリティカル セクションがないので実行されません。|  
  
## <a name="remarks"></a>コメント  
 `CComFakeCriticalSection`含まれるメソッドをミラー化[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)します。 ただし、`CComFakeCriticalSection`に重要なセクションの管轄外そのため、そのメソッドが何も行いません。  
  
 通常、使用して`CComFakeCriticalSection`を通じて、`typedef`名前か、`AutoCriticalSection`または`CriticalSection`です。 使用する場合[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)または[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)、これらの両方の`typedef`名前参照`CComFakeCriticalSection`します。 使用する場合[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)を参照している[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)と`CComCriticalSection`、それぞれします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
##  <a name="init"></a>CComFakeCriticalSection::Init  
 クリティカル セクションがないので実行されません。  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
##  <a name="lock"></a>CComFakeCriticalSection::Lock  
 クリティカル セクションがないので実行されません。  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
##  <a name="term"></a>CComFakeCriticalSection::Term  
 クリティカル セクションがないので実行されません。  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
##  <a name="unlock"></a>CComFakeCriticalSection::Unlock  
 クリティカル セクションがないので実行されません。  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

