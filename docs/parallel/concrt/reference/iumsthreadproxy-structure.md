---
title: "IUMSThreadProxy 構造体 | Microsoft Docs"
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
  - "concrtrm/concurrency::IUMSThreadProxy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSThreadProxy 構造体"
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IUMSThreadProxy 構造体
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

実行スレッドの抽象化です。  ユーザー モード スケジュール可能 \(UMS\) スレッドをスケジューラに付与するには、スケジューラ ポリシー要素 `SchedulerKind` の値を `UmsThreadDefault` に設定し、さらに `IUMSScheduler` インターフェイスを実装する必要があります。  UMS スレッドは、Windows 7 以上のバージョンの 64 ビット オペレーティング システムでのみサポートされます。  
  
## 構文  
  
```  
struct IUMSThreadProxy : public IThreadProxy;  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IUMSThreadProxy::EnterCriticalRegion メソッド](../Topic/IUMSThreadProxy::EnterCriticalRegion%20Method.md)|クリティカル領域に入るときに呼び出します。  クリティカル領域内のコードが実行されている間に生じた非同期のブロック操作をスケジューラは一切監視しません。  これは、スケジューラがページ フォールト、スレッドの中断、カーネルの非同期プロシージャ呼び出し \(APCs\) に対してなど、UMS スレッド再入されないことを意味します。|  
|[IUMSThreadProxy::EnterHyperCriticalRegion メソッド](../Topic/IUMSThreadProxy::EnterHyperCriticalRegion%20Method.md)|ハイパー クリティカル領域に入るときに呼び出します。  ハイパー クリティカル領域内のコードが実行されている間に生じたブロック操作をスケジューラは一切監視しません。  これは、スケジューラがの関数呼び出し、ブロック ロックの取得、ページ フォールト、スレッドの中断、カーネルの非同期プロシージャ呼び出し \(APCs\) など、ブロックする UMS スレッド再入されないことを意味します。|  
|[IUMSThreadProxy::ExitCriticalRegion メソッド](../Topic/IUMSThreadProxy::ExitCriticalRegion%20Method.md)|クリティカル領域から抜けるときに呼び出します。|  
|[IUMSThreadProxy::ExitHyperCriticalRegion メソッド](../Topic/IUMSThreadProxy::ExitHyperCriticalRegion%20Method.md)|ハイパー クリティカル領域から抜けるときに呼び出します。|  
|[IUMSThreadProxy::GetCriticalRegionType メソッド](../Topic/IUMSThreadProxy::GetCriticalRegionType%20Method.md)|スレッド プロキシが存在するクリティカル領域の種類を返します。  次にハイパー クリティカル領域がクリティカル領域のスーパーセットであるため、コードがクリティカル領域とハイパー クリティカル領域を入力すると、`InsideHyperCriticalRegion` が返されます。|  
  
## 継承階層  
 [IThreadProxy](../../../parallel/concrt/reference/ithreadproxy-structure.md)  
  
 `IUMSThreadProxy`  
  
## 必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IUMSScheduler 構造体](../../../parallel/concrt/reference/iumsscheduler-structure.md)   
 [SchedulerType 列挙型](../Topic/SchedulerType%20Enumeration.md)