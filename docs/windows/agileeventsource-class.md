---
title: AgileEventSource クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::AgileEventSource
- event/Microsoft::WRL::InvokeModeOptions
dev_langs:
- C++
helpviewer_keywords:
- AgileEventSource class
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7d025fc2be86fb5b59107d1deee39962c3c6db04
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2018
---
# <a name="agileeventsource-class"></a>AgileEventSource クラス
アジャイルのイベントを表します。 継承[EventSource](eventsource-class.md)し、上書き、`Add`アジャイルのイベントを起動する方法のオプションを指定する追加の型パラメーターを持つメンバー関数。
  
## <a name="syntax"></a>構文  
  
```  
template<typename TDelegateInterface, typename TEventSourceOptions = Microsoft::WRL::InvokeModeOptions<FireAll>>
class AgileEventSource
    : public Microsoft::WRL::EventSource<TDelegateInterface, TEventSourceOptions>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `TDelegateInterface`  
 デリゲートをイベント ハンドラーを表すインターフェイス。

 `TEventSourceOptions` [InvokeModeOptions](invokemodeoptions-structure.md) invokeMode フィールドに設定されている構造`InvokeMode::StopOnFirstError`または`InvokeMode::FireAll`です。

## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[AgileEventSource::Add メソッド](#add)|現在の AgileEventSource オブジェクトのイベント ハンドラーのセットを指定したデリゲート インターフェイスによって表される、アジャイルのイベント ハンドラーを追加します。|  

## <a name="add"></a> AgileEventSource::Add メソッド

現在の EventSource オブジェクトのイベント ハンドラーのセットを指定したデリゲート インターフェイスによって表されるイベント ハンドラーを追加します。

### <a name="syntax"></a>構文

```cpp
HRESULT Add(  
   _In_ TDelegateInterface* delegateInterface,  
   _Out_ EventRegistrationToken* token  
);
```

### <a name="parameters"></a>パラメーター

*delegateInterface*

インターフェイス、デリゲート オブジェクト、イベント ハンドラーを表します。

*トークン*この操作の完了時、イベントを表すハンドル。 Remove() メソッドにパラメーターとしてこのトークンを使用して、イベント ハンドラーを破棄します。

### <a name="return-value"></a>戻り値
成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="inheritance-hierarchy"></a>継承階層  
 `EventSource`  
 `AgileEventSource`
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)