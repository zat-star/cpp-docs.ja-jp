---
title: "CNoWorkerThread クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CNoWorkerThread"
  - "ATL.CNoWorkerThread"
  - "CNoWorkerThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNoWorkerThread クラス"
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CNoWorkerThread クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

動的キャッシュ管理を無効にする場合は `MonitorClass` のテンプレート パラメーターは、クラスをキャッシュできるように引数としてこのクラスを使用します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CNoWorkerThread  
  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CNoWorkerThread::AddHandle](../Topic/CNoWorkerThread::AddHandle.md)|[CWorkerThread::AddHandle](../Topic/CWorkerThread::AddHandle.md)の、機能的に同じです。|  
|[CNoWorkerThread::AddTimer](../Topic/CNoWorkerThread::AddTimer.md)|[CWorkerThread::AddTimer](../Topic/CWorkerThread::AddTimer.md)の、機能的に同じです。|  
|[CNoWorkerThread::GetThreadHandle](../Topic/CNoWorkerThread::GetThreadHandle.md)|[CWorkerThread::GetThreadHandle](../Topic/CWorkerThread::GetThreadHandle.md)の、機能的に同じです。|  
|[CNoWorkerThread::GetThreadId](../Topic/CNoWorkerThread::GetThreadId.md)|[CWorkerThread::GetThreadId](../Topic/CWorkerThread::GetThreadId.md)の、機能的に同じです。|  
|[CNoWorkerThread::Initialize](../Topic/CNoWorkerThread::Initialize.md)|[CWorkerThread::Initialize](../Topic/CWorkerThread::Initialize.md)の、機能的に同じです。|  
|[CNoWorkerThread::RemoveHandle](../Topic/CNoWorkerThread::RemoveHandle.md)|[CWorkerThread::RemoveHandle](../Topic/CWorkerThread::RemoveHandle.md)の、機能的に同じです。|  
|[CNoWorkerThread::Shutdown](../Topic/CNoWorkerThread::Shutdown.md)|[CWorkerThread::Shutdown](../Topic/CWorkerThread::Shutdown.md)の、機能的に同じです。|  
  
## 解説  
 このクラスは [CWorkerThread](../Topic/CWorkerThread%20Class.md)と同じパブリック インターフェイスを提供します。  このインターフェイスは、キャッシュ クラスに `MonitorClass` のテンプレート パラメーターによって提供されることになります。  
  
 このクラスのメソッドは何も実行しないために実装されます。  HRESULT は、常に S\_OK を返すメソッドは、処理またはスレッド ID 0 が常にを返すメソッド。  
  
## 必要条件  
 **Header:** atlutil.h