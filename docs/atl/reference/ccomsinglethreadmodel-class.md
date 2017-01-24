---
title: "CComSingleThreadModel クラス | Microsoft Docs"
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
  - "ATL.CComSingleThreadModel"
  - "CComSingleThreadModel"
  - "ATL::CComSingleThreadModel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComSingleThreadModel クラス"
  - "シングルスレッド アプリケーション"
  - "シングルスレッド アプリケーション, ATL"
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComSingleThreadModel クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、変数の値をインクリメントおよびデクリメントするための各種メソッドが用意されています。  
  
## 構文  
  
```  
  
class CComSingleThreadModel  
  
```  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|[CComSingleThreadModel::AutoCriticalSection](../Topic/CComSingleThreadModel::AutoCriticalSection.md)|参照クラス [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)。|  
|[CComSingleThreadModel::CriticalSection](../Topic/CComSingleThreadModel::CriticalSection.md)|参照クラス `CComFakeCriticalSection`。|  
|[CComSingleThreadModel::ThreadModelNoCS](../Topic/CComSingleThreadModel::ThreadModelNoCS.md)|`CComSingleThreadModel`を参照します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComSingleThreadModel::Decrement](../Topic/CComSingleThreadModel::Decrement.md)|指定された変数の値をデクリメントします。  この実装はスレッド セーフではありません。|  
|[CComSingleThreadModel::Increment](../Topic/CComSingleThreadModel::Increment.md)|指定された変数の値をインクリメントします。  この実装はスレッド セーフではありません。|  
  
## 解説  
 `CComSingleThreadModel` は、変数の値をインクリメントおよびデクリメントするためのメソッドを提供します。  [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) と [CComMultiThreadModelNoCS](../Topic/CComMultiThreadModelNoCS%20Class.md)とは異なり、これらのメソッドはスレッド セーフではありません。  
  
 通常、`typedef` の 2 種類の名前の 1 によって `CComSingleThreadModel` を [CComObjectThreadModel](../Topic/CComObjectThreadModel.md)、または [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)使用します。  各 `typedef` によって参照されるクラスは、次の表に示すように、使用するスレッド モデルによって異なります:  
  
|typedef|シングルスレッド モデル|アパートメント スレッド モデル|free なスレッド モデル|  
|-------------|------------------|----------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S\=`CComSingleThreadModel`; M\=`CComMultiThreadModel`  
  
 `CComSingleThreadModel` 自体は `typedef` の 3 種類の名前を定義します。  `ThreadModelNoCS` の参照 `CComSingleThreadModel`。  `AutoCriticalSection` と空のメソッドを提供します `CriticalSection` の参照 [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)クラスのクリティカル セクションの所有権を取得および解放に関連付けられています。  
  
## 必要条件  
 atlbase.h**Header:**  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)