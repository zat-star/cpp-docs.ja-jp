---
title: "task_handle クラス | Microsoft Docs"
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
  - "ppl/concurrency::task_handle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_handle クラス"
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
caps.latest.revision: 23
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# task_handle クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`task_handle` クラスは個々の並列作業項目を表します。  このクラスは、1 つの処理を実行するために必要な命令およびデータをカプセル化します。  
  
## 構文  
  
```  
template<  
   typename _Function  
>  
class task_handle : public ::Concurrency::details::_UnrealizedChore;  
```  
  
#### パラメーター  
 `_Function`  
 `task_handle` オブジェクトで表される処理を実行するために呼び出される関数オブジェクトの種類。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[task\_handle::task\_handle コンストラクター](../Topic/task_handle::task_handle%20Constructor.md)|新しい `task_handle` オブジェクトを構築します。  タスクの処理は、コンストラクターのパラメーターとして指定された関数を呼び出すことで実行されます。|  
|[task\_handle::~task\_handle デストラクター](../Topic/task_handle::~task_handle%20Destructor.md)|`task_handle` オブジェクトを破棄します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[task\_handle::operator\(\) 演算子](../Topic/task_handle::operator\(\)%20Operator.md)|タスク ハンドルの処理を実行するためにランタイムによって呼び出される関数呼び出し演算子。|  
  
## 解説  
 `task_handle` オブジェクトを `structured_task_group` オブジェクトと、または一般的な `task_group` オブジェクトと組み合わせて使用して、処理を並列タスクに分解できます。  詳細については、「[タスクの並列化](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)」を参照してください。  
  
 作成された `task_handle` オブジェクトの有効期間は、同時実行ランタイムで必要とされなくなるまで、`task_handle` オブジェクトの作成元によって管理されます。  通常、これは、配置先のキューがある `task_group` または `structured_task_group` の `wait` メソッドまたは `run_and_wait` メソッドが呼び出されるまで、`task_handle` オブジェクトが破棄されないことを意味します。  
  
 `task_handle` オブジェクトは、通常、C\+\+ のラムダと組み合わせて使用します。  ラムダの実際の型はわからないため、通常、[make\_task](../Topic/make_task%20Function.md) 関数を使用して `task_handle` オブジェクトを作成します。  
  
 `task_handle` オブジェクトに渡される処理関数のコピーは、ランタイムによって作成されます。  そのため、`task_handle` オブジェクトに渡した関数オブジェクトで発生した状態の変化は、その関数オブジェクトのコピーには反映されません。  
  
## 継承階層  
 `task_handle`  
  
## 必要条件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task\_group クラス](../Topic/task_group%20Class.md)   
 [structured\_task\_group クラス](../../../parallel/concrt/reference/structured-task-group-class.md)   
 [make\_task 関数](../Topic/make_task%20Function.md)   
 [task\_group::run メソッド](../Topic/task_group::run%20Method.md)   
 [task\_group::wait メソッド](../Topic/task_group::wait%20Method.md)   
 [task\_group::run\_and\_wait メソッド](../Topic/task_group::run_and_wait%20Method.md)   
 [structured\_task\_group::run メソッド](../Topic/structured_task_group::run%20Method.md)   
 [structured\_task\_group::wait メソッド](../Topic/structured_task_group::wait%20Method.md)   
 [structured\_task\_group::run\_and\_wait メソッド](../Topic/structured_task_group::run_and_wait%20Method.md)