---
title: "EventSource クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::EventSource
dev_langs: C++
helpviewer_keywords: EventSource class
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 705260547d5a42b463d61b79c38592874f9dfa19
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="eventsource-class"></a>EventSource クラス
イベントを表します。 EventSource メンバー関数は、追加、削除、およびイベント ハンドラーを呼び出します。  
  
## <a name="syntax"></a>構文  
  
```  
template<  
   typename TDelegateInterface  
>  
class EventSource;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TDelegateInterface`  
 デリゲートをイベント ハンドラーを表すインターフェイス。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[EventSource::EventSource コンストラクター](../windows/eventsource-eventsource-constructor.md)|EventSource クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[EventSource::Add メソッド](../windows/eventsource-add-method.md)|現在の EventSource オブジェクトのイベント ハンドラーのセットを指定したデリゲート インターフェイスによって表されるイベント ハンドラーを追加します。|  
|[EventSource::GetSize メソッド](../windows/eventsource-getsize-method.md)|現在の EventSource オブジェクトに関連付けられているイベント ハンドラーの数を取得します。|  
|[EventSource::InvokeAll メソッド](../windows/eventsource-invokeall-method.md)|指定した引数型と引数を使用して現在の EventSource オブジェクトに関連付けられている各イベント ハンドラーを呼び出します。|  
|[EventSource::Remove メソッド](../windows/eventsource-remove-method.md)|現在の EventSource オブジェクトに関連付けられているイベント ハンドラーのセットから指定したイベント登録トークンによって表されるイベント ハンドラーを削除します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[EventSource::addRemoveLock_ データ メンバー](../windows/eventsource-addremovelock-data-member.md)|アクセスを同期化、 [targets _](../windows/eventsource-targets-data-member.md)配列を追加する場合、削除、またはイベント ハンドラーの呼び出しです。|  
|[EventSource::targets_ データ メンバー](../windows/eventsource-targets-data-member.md)|1 つまたは複数のイベント ハンドラーの配列。|  
|[EventSource::targetsPointerLock_ データ メンバー](../windows/eventsource-targetspointerlock-data-member.md)|この EventSource のイベント ハンドラーが追加されている中であっても、削除、または呼び出される内部データ メンバーへのアクセスを同期します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `EventSource`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)