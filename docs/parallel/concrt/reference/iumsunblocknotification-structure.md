---
title: "IUMSUnblockNotification 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
dev_langs: C++
helpviewer_keywords: IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3febe10f7c71e1c1d478dd6f6b6f565c4134e033
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
|[Iumsunblocknotification::getcontext](#getcontext)|返します、`IExecutionContext`ブロック解除、スレッド プロキシに関連付けられている実行コンテキストのインターフェイスです。 このメソッドが戻るし、基になる実行コンテキストは呼び出しを経由してスケジュールが変更された後、`IThreadProxy::SwitchTo`メソッドでは、このインターフェイスは無効になりました。|  
|[Iumsunblocknotification::getnextunblocknotification](#getnextunblocknotification)|次を返します`IUMSUnblockNotification`メソッドから返されたチェーン内のインターフェイス`IUMSCompletionList::GetUnblockNotifications`です。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IUMSUnblockNotification`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="getcontext"></a>Iumsunblocknotification::getcontext メソッド  
 返します、`IExecutionContext`ブロック解除、スレッド プロキシに関連付けられている実行コンテキストのインターフェイスです。 このメソッドが戻るし、基になる実行コンテキストは呼び出しを経由してスケジュールが変更された後、`IThreadProxy::SwitchTo`メソッドでは、このインターフェイスは無効になりました。  
  
```
virtual IExecutionContext* GetContext() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 `IExecutionContext`スレッド プロキシがブロック解除する実行コンテキストのインターフェイスです。  
  
##  <a name="getnextunblocknotification"></a>Iumsunblocknotification::getnextunblocknotification メソッド  
 次を返します`IUMSUnblockNotification`メソッドから返されたチェーン内のインターフェイス`IUMSCompletionList::GetUnblockNotifications`です。  
  
```
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 次`IUMSUnblockNotification`メソッドから返されたチェーン内のインターフェイス`IUMSCompletionList::GetUnblockNotifications`です。  
  
## <a name="see-also"></a>参照  
 [同時実行 Namespace](concurrency-namespace.md)   
 [IUMSScheduler 構造体](iumsscheduler-structure.md)   
 [IUMSCompletionList 構造体](iumscompletionlist-structure.md)
