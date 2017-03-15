---
title: "EventTargetArray クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::EventTargetArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EventTargetArray クラス"
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# EventTargetArray クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
class EventTargetArray : public Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<ClassicCom>, IUnknown>;  
```  
  
## <a name="remarks"></a>コメント  
 イベント ハンドラーの配列を表します。  
  
 イベント ハンドラーに関連付けられている、 [EventSource](../windows/eventsource-class.md) オブジェクトは、保護された EventTargetArray データ メンバーに格納されます。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Eventtargetarray::eventtargetarray コンス トラクター](../windows/eventtargetarray-eventtargetarray-constructor.md)|EventTargetArray クラスの新しいインスタンスを初期化します。|  
|[EventTargetArray:: ~ EventTargetArray デストラクター](../Topic/EventTargetArray::~EventTargetArray%20Destructor.md)|現在の EventTargetArray クラスの初期化を解除します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Eventtargetarray::addtail メソッド](../windows/eventtargetarray-addtail-method.md)|指定したイベント ハンドラーをイベント ハンドラーの内部配列の末尾に追加します。|  
|[Eventtargetarray::begin メソッド](../windows/eventtargetarray-begin-method.md)|イベント ハンドラーの内部配列の最初の要素のアドレスを取得します。|  
|[Eventtargetarray::end メソッド](../windows/eventtargetarray-end-method.md)|イベント ハンドラーの内部配列の最後の要素のアドレスを取得します。|  
|[Eventtargetarray::length メソッド](../windows/eventtargetarray-length-method.md)|イベント ハンドラーの内部配列の要素の現在の数を取得します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `EventTargetArray`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)