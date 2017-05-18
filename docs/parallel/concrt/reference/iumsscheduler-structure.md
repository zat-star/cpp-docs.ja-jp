---
title: "IUMSScheduler 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler::IUMSScheduler::SetCompletionList
dev_langs:
- C++
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
caps.latest.revision: 18
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
ms.openlocfilehash: 58ca59224b5d9cdeb282562349642736a1b22c74
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="iumsscheduler-structure"></a>IUMSScheduler 構造体
同時実行ランタイムのリソース マネージャーによってユーザー モード スケジュール可能 (UMS) スレッドが渡される必要がある作業スケジューラの抽象化のインターフェイスです。 リソース マネージャーでは、このインターフェイスを使用して UMS スレッド スケジューラと通信します。 `IUMSScheduler` インターフェイスは `IScheduler` インターフェイスを継承します。  
  
## <a name="syntax"></a>構文  
  
```
struct IUMSScheduler : public IScheduler;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Iumsscheduler::setcompletionlist](#setcompletionlist)|代入、 `IUMSCompletionList` UMS スレッド スケジューラへのインターフェイスです。|  
  
## <a name="remarks"></a>コメント  
 リソース マネージャーとの通信を行うカスタム スケジューラを実装している通常の Win32 スレッドの代わりに、スケジューラに渡す UMS スレッドが必要な場合は、実装を提供する必要があります、`IUMSScheduler`インターフェイスです。 さらに、スケジューラ ポリシー キーのポリシーの値を設定する必要があります`SchedulerKind`する`UmsThreadDefault`です。 UMS スレッドが、ポリシーに指定した場合、`IScheduler`インターフェイスへのパラメーターとして渡される、 [iresourcemanager::registerscheduler](iresourcemanager-structure.md#registerscheduler)メソッドである必要があります、`IUMSScheduler`インターフェイスです。  
  
 リソース マネージャーでは、UMS 機能を持つオペレーティング システムでのみ、UMS スレッドです。 Windows 7 以上のバージョンの 64 ビット オペレーティング システムでは、UMS スレッドをサポートします。 スケジューラを使用してポリシーを作成する場合、`SchedulerKind`キー、値に設定`UmsThreadDefault`基になるプラットフォームでは、UMS の値をサポートしていない、`SchedulerKind`そのポリシーのキーは、値に変更されます`ThreadScheduler`します。 必ず確認してこのポリシーの値 UMS スレッドが表示されることを想定します。  
  
 `IUMSScheduler`インターフェイスは&1; つの側のスケジューラとリソース マネージャー間の通信の双方向チャネル。 もう一方の端がによって表される、`IResourceManager`と`ISchedulerProxy`インターフェイスで、リソース マネージャーでは実装されています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [IScheduler](ischeduler-structure.md)  
  
 `IUMSScheduler`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="setcompletionlist"></a>Iumsscheduler::setcompletionlist メソッド  
 代入、 `IUMSCompletionList` UMS スレッド スケジューラへのインターフェイスです。  
  
```
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pCompletionList`  
 スケジューラの完了リスト インターフェイスです。 スケジューラあたり&1; つのリストがあります。  
  
### <a name="remarks"></a>コメント  
 リソース マネージャーでは、スケジューラがリソースの最初の割り当てを要求されたら UMS スレッドが必要であるスケジューラでは、このメソッドを呼び出します。 スケジューラを使用して、 `IUMSCompletionList` UMS スレッド プロキシがブロックされない場合を判断するインターフェイスです。 UMS スケジューラに割り当てられている仮想プロセッサ ルートで実行中のスレッド プロキシからこのインターフェイスにアクセスすることはのみです。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [IScheduler 構造体](ischeduler-structure.md)   
 [IUMSCompletionList 構造体](iumscompletionlist-structure.md)   
 [IResourceManager 構造体](iresourcemanager-structure.md)

