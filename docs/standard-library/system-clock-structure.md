---
title: "system_clock 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "chrono/std::chrono::system_clock"
dev_langs: 
  - "C++"
ms.assetid: a97bd46e-267a-4836-9f7d-af1f664e99ae
caps.latest.revision: 14
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# system_clock 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

システムのリアルタイム クロックに基づく*クロックの型*を表します。  
  
## 構文  
  
```  
struct system_clock;  
```  
  
## 解説  
 *クロック型*は、UTC で現在時刻を取得するために使用されます。  型は [duration](../standard-library/duration-class.md) とクラス テンプレート [time\_point](../standard-library/time-point-class.md) のインスタンス化を具体化し、時間を返す静的メンバー関数 `now()` を定義します。  
  
 *単調* への最初の呼び出しによって返される値が、`now()` への以降の呼び出しによって返される値以下である場合、クロックは常に`now()`になります。  
  
 *単調*で、クロックのティック間の時間が一定のクロックは*安定しています*。  
  
 この実装では、`system_clock` は `high_resolution_clock` と同じ意味です。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`system_clock::duration`|`duration<rep, period>` と同義。|  
|`system_clock::period`|`duration` に含まれるインスタンス化のティック間隔を表すために使用される型と同義です。|  
|`system_clock::rep`|`duration` に含まれるインスタンス化のクロック ティックの数を表すために使用される型と同義です。|  
|`system_clock::time_point`|`time_point<Clock, duration>` と同義です。ここで、`Clock` はクロック型自体または同じエポックに基づいた別のクロック型と同義で、同じ入れ子になった `duration` 型を持っています。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[system\_clock::from\_time\_t メソッド](../Topic/system_clock::from_time_t%20Method.md)|静的。  指定された時間に最も近い `time_point` を返します。|  
|[system\_clock::now メソッド](../Topic/system_clock::now%20Method.md)|静的。  現在の時間を返します。|  
|[system\_clock::to\_time\_t メソッド](../Topic/system_clock::to_time_t%20Method.md)|静的。  指定された `time_t` に最も近い `time_point` オブジェクトを返します。|  
  
### パブリック定数  
  
|名前|説明|  
|--------|--------|  
|[system\_clock::is\_monotonic 定数](../Topic/system_clock::is_monotonic%20Constant.md)|クロック型が単調かどうかを指定します。|  
|[system\_clock::is\_steady 定数](../Topic/system_clock::is_steady%20Constant.md)|クロック型が一定かどうかを指定します。|  
  
## 必要条件  
 **ヘッダー:** chrono  
  
 **名前空間:** std::chrono  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)   
 [steady\_clock 構造体](../Topic/steady_clock%20struct.md)