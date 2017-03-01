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
- concrtrm/concurrency::IUMSCompletionList
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 25023c27244669092e0f57fe59bdb190fd2f2afb
ms.lasthandoff: 02/24/2017

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
|[Iumscompletionlist::getunblocknotifications メソッド](#getunblocknotifications)|チェーンを取得`IUMSUnblockNotification`プロキシは、このメソッドの前回に排除されてはいませんが関連付けられているスレッドが呼び出された実行コンテキストを表すインターフェイスです。|  
  
## <a name="remarks"></a>コメント  
 スケジューラは、コンプリート リストから項目をキューから削除するには、このインターフェイスを使用して後で実行される操作について十分に注意する必要があります。 項目では、実行可能なコンテキストのスケジューラの一覧に置く必要があり、できるだけ早くで一般的にアクセスできるようにします。 これでは、キューから取り出された項目のいずれかを設定した任意のロックの所有権。 スケジューラはアイテムをキューから削除する呼び出しと一般にアクセスできるからスケジューラ内でリストにこれらのアイテムの配置の間ブロックできる任意の関数呼び出しを行うことがないことができます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IUMSCompletionList`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namegetunblocknotificationsa--iumscompletionlistgetunblocknotifications-method"></a><a name="getunblocknotifications"></a>Iumscompletionlist::getunblocknotifications メソッド  
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

