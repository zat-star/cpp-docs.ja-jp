---
title: "IUMSCompletionList 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
dev_langs:
- C++
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 65655e4e03a7b187e0bbadbd576bc088bb57f7c8
ms.lasthandoff: 03/17/2017

---
# <a name="iumscompletionlist-structure"></a>IUMSCompletionList 構造体
UMS の完了リストを表します。 UMS スレッドがブロックされると、基になる仮想プロセッサ ルートでスケジュールする内容を決定するためにスケジューラで指定されているスケジュールのコンテキストがディスパッチされ、元のスレッドがブロックされます。 元のスレッドがブロックされない場合、オペレーション システムは、このインターフェイスからアクセスできる完了リストのキューにそれを配置します。 スケジューラは指定されたスケジュール コンテキスト、または作業を検索するその他の場所にある完了リストを照会できます。  
  
## <a name="syntax"></a>構文  
  
```
struct IUMSCompletionList;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Iumscompletionlist::getunblocknotifications](#getunblocknotifications)|チェーンを取得`IUMSUnblockNotification`プロキシは、このメソッドの前回に排除されてはいませんが関連付けられているスレッドが呼び出された実行コンテキストを表すインターフェイスです。|  
  
## <a name="remarks"></a>コメント  
 スケジューラは、コンプリート リストから項目をキューから削除するには、このインターフェイスを使用して後で実行される操作について十分に注意する必要があります。 項目では、実行可能なコンテキストのスケジューラの一覧に置く必要があり、できるだけ早くで一般的にアクセスできるようにします。 これでは、キューから取り出された項目のいずれかを設定した任意のロックの所有権。 スケジューラはアイテムをキューから削除する呼び出しと一般にアクセスできるからスケジューラ内でリストにこれらのアイテムの配置の間ブロックできる任意の関数呼び出しを行うことがないことができます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IUMSCompletionList`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="getunblocknotifications"></a>Iumscompletionlist::getunblocknotifications メソッド  
 チェーンを取得`IUMSUnblockNotification`プロキシは、このメソッドの前回に排除されてはいませんが関連付けられているスレッドが呼び出された実行コンテキストを表すインターフェイスです。  
  
```
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 チェーン`IUMSUnblockNotification`インターフェイスです。  
  
### <a name="remarks"></a>コメント  
 実行コンテキストが再スケジュールされると、返される通知は有効ではありません。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [IUMSScheduler 構造体](iumsscheduler-structure.md)   
 [IUMSUnblockNotification 構造体](iumsunblocknotification-structure.md)

