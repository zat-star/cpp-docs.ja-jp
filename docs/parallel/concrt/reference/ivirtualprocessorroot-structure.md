---
title: "IVirtualProcessorRoot 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IVirtualProcessorRoot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IVirtualProcessorRoot 構造体"
ms.assetid: 5ef371b8-9e4f-4fef-bb0d-49099693dd2b
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# IVirtualProcessorRoot 構造体
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

スレッド プロキシが実行できるハードウェア スレッドの抽象化です。  
  
## 構文  
  
```  
struct IVirtualProcessorRoot : public IExecutionResource;  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IVirtualProcessorRoot::Activate メソッド](../Topic/IVirtualProcessorRoot::Activate%20Method.md)|実行コンテキスト インターフェイス `pContext` に関連付けられているスレッド プロキシに、この仮想プロセッサ ルートでの実行を開始させます。|  
|[IVirtualProcessorRoot::Deactivate メソッド](../Topic/IVirtualProcessorRoot::Deactivate%20Method.md)|この仮想プロセッサ ルートで現在実行されているスレッド プロキシに、実行コンテキストのディスパッチを中止させます。  スレッド プロキシは、`Activate` メソッドの呼び出しで実行を再開します。|  
|[IVirtualProcessorRoot::EnsureAllTasksVisible メソッド](../Topic/IVirtualProcessorRoot::EnsureAllTasksVisible%20Method.md)|各プロセッサのメモリ階層に格納されているデータを、システム上のすべてのプロセッサから参照できるようにします。  メモリ フェンス全体がすべてのプロセッサで実行された後で、メソッドから制御が返されます。|  
|[IVirtualProcessorRoot::GetId メソッド](../Topic/IVirtualProcessorRoot::GetId%20Method.md)|仮想プロセッサ ルートの一意の識別子を返します。|  
  
## 解説  
 すべての仮想プロセッサ ルートには、実行リソースが関連付けられます。  `IVirtualProcessorRoot` インターフェイスは、[IExecutionResource](../../../parallel/concrt/reference/iexecutionresource-structure.md) インターフェイスから継承されます。  基になる同じハードウェア スレッドに対して複数の仮想プロセッサ ルートが対応する場合もあります。  
  
 リソース マネージャーは、リソース要求に応える形で、仮想プロセッサ ルートをスケジューラに付与します。  スケジューラは、仮想プロセッサ ルートを実行コンテキストでアクティブ化することによって、その仮想プロセッサ ルートで処理を実行できます。  
  
## 継承階層  
 [IExecutionResource](../../../parallel/concrt/reference/iexecutionresource-structure.md)  
  
 `IVirtualProcessorRoot`  
  
## 必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)