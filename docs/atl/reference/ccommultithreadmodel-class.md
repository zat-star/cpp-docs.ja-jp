---
title: "CComMultiThreadModel クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComMultiThreadModel"
  - "ATL.CComMultiThreadModel"
  - "ATL::CComMultiThreadModel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, マルチスレッド"
  - "CComMultiThreadModel クラス"
  - "スレッド処理 [ATL]"
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComMultiThreadModel クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComMultiThreadModel` は、変数の値をインクリメントおよびデクリメントするためのスレッドセーフなメソッドが用意されています。  
  
## 構文  
  
```  
  
class CComMultiThreadModel  
  
```  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|[CComMultiThreadModel::AutoCriticalSection](../Topic/CComMultiThreadModel::AutoCriticalSection.md)|参照クラス [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)。|  
|[CComMultiThreadModel::CriticalSection](../Topic/CComMultiThreadModel::CriticalSection.md)|参照クラス [CComCriticalSection](../Topic/CComCriticalSection%20Class.md)。|  
|[CComMultiThreadModel::ThreadModelNoCS](../Topic/CComMultiThreadModel::ThreadModelNoCS.md)|参照クラス [CComMultiThreadModelNoCS](../Topic/CComMultiThreadModelNoCS%20Class.md)。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComMultiThreadModel::Decrement](../Topic/CComMultiThreadModel::Decrement.md)|\(静的\) スレッド セーフな方法で指定された変数の値をデクリメントします。|  
|[CComMultiThreadModel::Increment](../Topic/CComMultiThreadModel::Increment.md)|\(静的\) スレッド セーフな方法で指定された変数の値をインクリメントします。|  
  
## 解説  
 通常、`typedef` の 2 種類の名前の 1 によって `CComMultiThreadModel` を [CComObjectThreadModel](../Topic/CComObjectThreadModel.md)、または [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)使用します。  各 `typedef` によって参照されるクラスは、次の表に示すように、使用するスレッド モデルによって異なります:  
  
|typedef|一つのスレッド|アパートメント スレッド|free なスレッド|  
|-------------|-------------|------------------|----------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S\=`CComSingleThreadModel`; M\=`CComMultiThreadModel`  
  
 `CComMultiThreadModel` 自体は `typedef` の 3 種類の名前を定義します。  `AutoCriticalSection` とクリティカル セクションの所有権を取得および解放するメソッドを提供するクラス `CriticalSection` の参照。  `ThreadModelNoCS` の参照を含むクラス [CComMultiThreadModelNoCS](../Topic/CComMultiThreadModelNoCS%20Class.md)。  
  
## 必要条件  
 atlbase.h**Header:**  
  
## 参照  
 [CComSingleThreadModel クラス](../../atl/reference/ccomsinglethreadmodel-class.md)   
 [CComAutoCriticalSection クラス](../../atl/reference/ccomautocriticalsection-class.md)   
 [CComCriticalSection クラス](../Topic/CComCriticalSection%20Class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)