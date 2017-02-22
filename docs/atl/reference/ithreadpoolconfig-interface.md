---
title: "IThreadPoolConfig インターフェイス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IThreadPoolConfig"
  - "ATL::IThreadPoolConfig"
  - "ATL.IThreadPoolConfig"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IThreadPoolConfig インターフェイス"
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# IThreadPoolConfig インターフェイス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このインターフェイスには、スレッド プールを設定するメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      __interface  
__declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660"))  
IThreadPoolConfig :  
public IUnknown  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[GetSize](../Topic/IThreadPoolConfig::GetSize.md)|プール内のスレッドの数を取得するときにこのメソッドを呼び出します。|  
|[GetTimeout](../Topic/IThreadPoolConfig::GetTimeout.md)|スレッド プールがシャットダウンするまでスレッドを待機するミリ秒単位の最大時間を取得するときにこのメソッドを呼び出します。|  
|[SetSize](../Topic/IThreadPoolConfig::SetSize.md)|プール内のスレッドの数を設定するには、このメソッドを呼び出します。|  
|[SetTimeout](../Topic/IThreadPoolConfig::SetTimeout.md)|スレッド プールがシャットダウンするまでスレッドを待機するミリ秒単位の最大時間を設定するには、このメソッドを呼び出します。|  
  
## 解説  
 このインターフェイスは [CThreadPool](../Topic/CThreadPool%20Class.md)によって実装されます。  
  
## 必要条件  
 **Header:** atlutil.h  
  
## 参照  
 [クラス](../../atl/reference/atl-classes.md)   
 [CThreadPool クラス](../Topic/CThreadPool%20Class.md)