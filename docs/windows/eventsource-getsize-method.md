---
title: "EventSource::GetSize メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource::GetSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetSize メソッド"
ms.assetid: 7825aab5-1a6b-465f-9159-3a6684142d1f
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# EventSource::GetSize メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

現在の EventSource オブジェクトに関連付けられているイベント ハンドラーの数を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
size_t GetSize() const;  
```  
  
## <a name="return-value"></a>戻り値  
 内のイベント ハンドラーの数 [targets _](../Topic/EventSource::targets_%20Data%20Member.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>「  
 [EventSource クラス](../windows/eventsource-class.md)