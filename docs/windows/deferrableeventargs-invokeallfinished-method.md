---
title: "DeferrableEventArgs::InvokeAllFinished メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 86b45205-3edb-4134-9cd0-ed7a7b4c3b1a
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DeferrableEventArgs::InvokeAllFinished メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

遅延イベントを処理するすべての処理が完了したことを示すために呼び出されます。  
  
## 構文  
  
```cpp  
void InvokeAllFinished()  
```  
  
## 解説  
 イベント ソースが [InvokeAll](../windows/eventsource-invokeall-method.md) を呼び出した後で、このメソッドを呼び出す必要があります。  このメソッドを呼び出すことで、さらに遅延が取られることを回避し、遅延が取られなかった場合は、完了ハンドラーの実行を強制します。  
  
 コード例は、[DeferrableEventArgs クラス](../windows/deferrableeventargs-class.md) を参照してください。  
  
## 必要条件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [DeferrableEventArgs クラス](../windows/deferrableeventargs-class.md)   
 [EventSource::InvokeAll メソッド](../windows/eventsource-invokeall-method.md)