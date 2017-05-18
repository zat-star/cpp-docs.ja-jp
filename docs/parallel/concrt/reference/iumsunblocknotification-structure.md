---
title: "IUMSUnblockNotification 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
dev_langs:
- C++
helpviewer_keywords:
- IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: ee9c1ada7718b948e5a038852bfa5514127324b1
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="iumsunblocknotification-structure"></a>IUMSUnblockNotification 構造体
ブロックされ、スケジューラの指定されたスケジュール コンテキストに制御を戻すことをトリガーされたスレッド プロキシが、ブロック解除され、スケジュールできる状態であることを示す、リソース マネージャーからの通知を表します。 このインターフェイスは、`GetContext` メソッドから返される、スレッド プロキシの関連付けられた実行コンテキストが再スケジュールされると無効になります。  
  
## <a name="syntax"></a>構文  
  
```
struct IUMSUnblockNotification;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Iumsunblocknotification::getcontext](#getcontext)|返します。、`IExecutionContext`ブロック解除されたスレッド プロキシに関連付けられている実行コンテキストのインターフェイスです。 このメソッドが戻るし、基になる実行コンテキストは呼び出しを経由してスケジュールが変更された後、`IThreadProxy::SwitchTo`メソッドでは、このインターフェイスが無効になっています。|  
|[Iumsunblocknotification::getnextunblocknotification](#getnextunblocknotification)|次を返す`IUMSUnblockNotification`メソッドから返されるチェーン内のインターフェイス`IUMSCompletionList::GetUnblockNotifications`します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IUMSUnblockNotification`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="getcontext"></a>Iumsunblocknotification::getcontext メソッド  
 返します。、`IExecutionContext`ブロック解除されたスレッド プロキシに関連付けられている実行コンテキストのインターフェイスです。 このメソッドが戻るし、基になる実行コンテキストは呼び出しを経由してスケジュールが変更された後、`IThreadProxy::SwitchTo`メソッドでは、このインターフェイスが無効になっています。  
  
```
virtual IExecutionContext* GetContext() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 `IExecutionContext`スレッド プロキシが排除されてはいませんが、実行コンテキストのインターフェイスです。  
  
##  <a name="getnextunblocknotification"></a>Iumsunblocknotification::getnextunblocknotification メソッド  
 次を返す`IUMSUnblockNotification`メソッドから返されるチェーン内のインターフェイス`IUMSCompletionList::GetUnblockNotifications`します。  
  
```
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 次の`IUMSUnblockNotification`メソッドから返されるチェーン内のインターフェイス`IUMSCompletionList::GetUnblockNotifications`します。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [IUMSScheduler 構造体](iumsscheduler-structure.md)   
 [IUMSCompletionList 構造体](iumscompletionlist-structure.md)

