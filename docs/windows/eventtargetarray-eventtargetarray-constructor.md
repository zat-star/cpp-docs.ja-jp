---
title: "EventTargetArray::EventTargetArray コンストラクター | Microsoft Docs"
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
  - "event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EventTargetArray、コンストラクター"
ms.assetid: 6c6d3737-3cd3-4515-a8f6-d27901bb8ed2
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# EventTargetArray::EventTargetArray コンストラクター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
EventTargetArray(  
   _Out_ HRESULT* hr,  
   size_t items  
);  
```  
  
#### パラメーター  
 `hr`  
 このコンストラクター操作の後に、パラメーター `hr` は成功したかどうか、または失敗した配列の割り当てを示します。  次の表に、`hr` の有効値を示します。  
  
 S\_OK  
 成功するアクション。  
  
 E\_OUTOFMEMORY  
 配列にメモリを割り当てることができませんでした。  
  
 S\_FALSE  
 パラメーター `items` はゼロ以下です。  
  
 `items`  
 割り当てる配列の要素数。  
  
## 解説  
 EventTargetArray クラスの新しいインスタンスを初期化します。  
  
 EventTargetArray が EventSource オブジェクトにイベント ハンドラーの配列を保持するために使用されます。  
  
## 必要条件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [EventTargetArray クラス](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)