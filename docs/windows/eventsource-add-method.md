---
title: "EventSource::Add メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource::Add"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Add メソッド"
ms.assetid: 8bded85b-929e-4425-a464-e5de67bb774c
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# EventSource::Add メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

現在の EventSource オブジェクトに対してイベント ハンドラーのセットに指定したデリゲート インターフェイスによって表されるイベント ハンドラーを追加します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT Add(  
   _In_ TDelegateInterface* delegateInterface,  
   _Out_ EventRegistrationToken* token  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `delegateInterface`  
 イベント ハンドラーを表すデリゲート オブジェクトへのインターフェイス。  
  
 `token`  
 この操作が完了したとき、イベントを表すハンドルです。 パラメーターとしてこのトークンを使用して、 [Remove()](../Topic/EventSource::Remove%20Method.md) メソッドをイベント ハンドラーを破棄します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [EventSource クラス](../windows/eventsource-class.md)