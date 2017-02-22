---
title: "EventSource クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EventSource クラス"
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# EventSource クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イベントを表します。  EventSource のメンバー関数は、イベント ハンドラーを追加、削除、および呼び出します。  
  
## 構文  
  
```  
template<  
   typename TDelegateInterface  
>  
class EventSource;  
```  
  
#### パラメーター  
 `TDelegateInterface`  
 イベント ハンドラーを表すデリゲートへのインターフェイス。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[EventSource::EventSource コンストラクター](../windows/eventsource-eventsource-constructor.md)|EventSource クラスの新しいインスタンスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[EventSource::Add メソッド](../windows/eventsource-add-method.md)|EventSource の現在のオブジェクトのイベント ハンドラーを設定する指定されたデリゲート インターフェイスで表されるイベント ハンドラーを追加します。|  
|[EventSource::GetSize メソッド](../windows/eventsource-getsize-method.md)|EventSource の現在のオブジェクトに関連付けられたイベント ハンドラーの数を取得します|  
|[EventSource::InvokeAll メソッド](../windows/eventsource-invokeall-method.md)|各イベント ハンドラーに指定された引数の型と引数を使用して EventSource の現在のオブジェクトに関連付けられた呼び出します。|  
|[EventSource::Remove メソッド](../Topic/EventSource::Remove%20Method.md)|指定したイベント トークンによって表される登録 EventSource の現在のオブジェクトに関連付けられたイベント ハンドラーのセットからイベント ハンドラーを削除します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[EventSource::addRemoveLock\_ データ メンバー](../windows/eventsource-addremovelock-data-member.md)|イベント ハンドラーを追加または削除したり、呼び出すと [targets\_](../Topic/EventSource::targets_%20Data%20Member.md) の配列へのアクセスを同期します。|  
|[EventSource::targets\_ データ メンバー](../Topic/EventSource::targets_%20Data%20Member.md)|一つ以上のイベント ハンドラーの配列。|  
|[EventSource::targetsPointerLock\_ データ メンバー](../windows/eventsource-targetspointerlock-data-member.md)|この EventSource のイベント ハンドラーが追加されているか、削除または呼び出されている内部データ メンバーへのアクセスを同期します。|  
  
## 継承階層  
 `EventSource`  
  
## 必要条件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)