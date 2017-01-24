---
title: "IResourceManager 構造体 | Microsoft Docs"
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
  - "concrtrm/concurrency::IResourceManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IResourceManager 構造体"
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
caps.latest.revision: 20
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IResourceManager 構造体
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

同時実行ランタイムのリソース マネージャーに対するインターフェイスです。  これは、スケジューラがリソース マネージャーと通信する際に使用されるインターフェイスです。  
  
## 構文  
  
```  
struct IResourceManager;  
```  
  
## メンバー  
  
### パブリック列挙型  
  
|名前|説明|  
|--------|--------|  
|[IResourceManager::OSVersion 列挙](../Topic/IResourceManager::OSVersion%20Enumeration.md)|オペレーティング システムのバージョンを表す列挙型。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IResourceManager::CreateNodeTopology メソッド](../Topic/IResourceManager::CreateNodeTopology%20Method.md)|デバッグ ビルド版のランタイムにのみ存在します。このメソッドは、構成に合わせた実際のハードウェアを用意することなく、さまざまなハードウェア トポロジに対してリソース マネージャーのテストを実行できるように設計されたテスト用メソッドです。  製品版のランタイムでは、このメソッドは処理を一切実行せずに操作を戻します。|  
|[IResourceManager::GetAvailableNodeCount メソッド](../Topic/IResourceManager::GetAvailableNodeCount%20Method.md)|使用できるリソース マネージャーにノードの数を返します。|  
|[IResourceManager::GetFirstNode メソッド](../Topic/IResourceManager::GetFirstNode%20Method.md)|リソース マネージャーによって定義されるように列挙体の順序に最初のノードを返します。|  
|[IResourceManager::Reference メソッド](../Topic/IResourceManager::Reference%20Method.md)|リソース マネージャー インスタンスで参照カウントをインクリメントします。|  
|[IResourceManager::RegisterScheduler メソッド](../Topic/IResourceManager::RegisterScheduler%20Method.md)|スケジューラをリソース マネージャーに登録します。  登録されたスケジューラは、返される `ISchedulerProxy` インターフェイスを使用してリソース マネージャーと通信します。|  
|[IResourceManager::Release メソッド](../Topic/IResourceManager::Release%20Method.md)|リソース マネージャー インスタンスで参照カウントをデクリメントします。  参照カウントが `0` になると、リソース マネージャーが破棄されます。|  
  
## 解説  
 [CreateResourceManager](../Topic/CreateResourceManager%20Function.md) 関数を使用して、リソース マネージャーのシングルトン インスタンスに対するインターフェイスを取得します。  このメソッドは、リソース マネージャーの参照カウントをインクリメントします。リソース マネージャーを使った操作が完了したら、[IResourceManager::Release](../Topic/IResourceManager::Release%20Method.md) メソッドを呼び出して参照を解放する必要があります。  通常、作成する各スケジューラで、作成中にこのメソッドが呼び出されます。スケジューラの終了後、リソース マネージャーへの参照が解放されます。  
  
## 継承階層  
 `IResourceManager`  
  
## 必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ISchedulerProxy 構造体](../../../parallel/concrt/reference/ischedulerproxy-structure.md)   
 [IScheduler 構造体](../../../parallel/concrt/reference/ischeduler-structure.md)