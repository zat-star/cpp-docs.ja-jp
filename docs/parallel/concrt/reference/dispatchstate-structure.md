---
title: "DispatchState 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DispatchState
- CONCRTRM/concurrency::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::m_dispatchStateSize
- CONCRTRM/concurrency::DispatchState::DispatchState::m_fIsPreviousContextAsynchronouslyBlocked
- CONCRTRM/concurrency::DispatchState::DispatchState::m_reserved
dev_langs:
- C++
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
caps.latest.revision: 17
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
ms.openlocfilehash: a617d1f1d7f68c00c7011daffc6ba59f08c43a1e
ms.lasthandoff: 03/17/2017

---
# <a name="dispatchstate-structure"></a>DispatchState 構造体
`DispatchState` 構造体は、状態を `IExecutionContext::Dispatch` メソッドに転送するために使用されます。 `Dispatch` メソッドが `IExecutionContext` インターフェイスで呼び出される状況を示します。  
  
## <a name="syntax"></a>構文  
  
```
struct DispatchState;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Dispatchstate::dispatchstate](#ctor)|新しい `DispatchState` オブジェクトを構築します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[Dispatchstate::m_dispatchstatesize](#m_dispatchstatesize)|バージョン管理に使用するこの構造体のサイズ。|  
|[Dispatchstate::m_fispreviouscontextasynchronouslyblocked](#m_fispreviouscontextasynchronouslyblocked)|このコンテキストが入力されているかどうかを指示、`Dispatch`メソッド以前のコンテキストが非同期的にブロックされているためです。 これは、UMS スケジュール コンテキストでのみ使用され、値に設定されている`0`他のすべての実行コンテキスト。|  
|[Dispatchstate::m_reserved](#m_reserved)|将来の情報を渡すために予約されてビットです。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `DispatchState`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a>Dispatchstate::dispatchstate コンス トラクター  
 新しい `DispatchState` オブジェクトを構築します。  
  
```
DispatchState();
```  
  
##  <a name="m_dispatchstatesize"></a>Dispatchstate::m_dispatchstatesize データ メンバー  
 バージョン管理に使用するこの構造体のサイズ。  
  
```
unsigned long m_dispatchStateSize;
```  
  
##  <a name="m_fispreviouscontextasynchronouslyblocked"></a>Dispatchstate::m_fispreviouscontextasynchronouslyblocked データ メンバー  
 このコンテキストが入力されているかどうかを指示、`Dispatch`メソッド以前のコンテキストが非同期的にブロックされているためです。 これは、UMS スケジュール コンテキストでのみ使用され、値に設定されている`0`他のすべての実行コンテキスト。  
  
```
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```  
  
##  <a name="m_reserved"></a>Dispatchstate::m_reserved データ メンバー  
 将来の情報を渡すために予約されてビットです。  
  
```
unsigned int m_reserved : 31;
```  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)

