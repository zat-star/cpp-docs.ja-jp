---
title: "CComSimpleThreadAllocator クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
dev_langs:
- C++
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 377e7f2fa6d8377d46e98b52e9c8f075b10956a8
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsimplethreadallocator-class"></a>CComSimpleThreadAllocator クラス
このクラスは、クラスのスレッドの選択、管理`CComAutoThreadModule`します。  
  
## <a name="syntax"></a>構文  
  
```
class CComSimpleThreadAllocator
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComSimpleThreadAllocator::GetThread](#getthread)|スレッドを選択します。|  
  
## <a name="remarks"></a>コメント  
 `CComSimpleThreadAllocator`スレッドの選択を管理する[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)します。 `CComSimpleThreadAllocator::GetThread`単に各スレッドが繰り返しをシーケンス内の次の&1; つを返します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="getthread"></a>CComSimpleThreadAllocator::GetThread  
 シーケンス内の次のスレッドを指定することによって、スレッドを選択します。  
  
```
int GetThread(CComApartment* /* pApt */, int nThreads);
```  
  
### <a name="parameters"></a>パラメーター  
 `pApt`  
 ATL の既定の実装では使用されません。  
  
 `nThreads`  
 EXE モジュール内のスレッドの最大数。  
  
### <a name="return-value"></a>戻り値  
 0 までの整数と ( `nThreads` – 1)。 EXE モジュールのスレッドの&1; つを識別します。  
  
### <a name="remarks"></a>コメント  
 オーバーライドできます`GetThread`選択範囲のさまざまなメソッドを提供したり、使用、`pApt`パラメーター。  
  
 `GetThread`によって呼び出される[CComAutoThreadModule::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance)します。  
  
## <a name="see-also"></a>関連項目  
 [CComApartment クラス](../../atl/reference/ccomapartment-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

