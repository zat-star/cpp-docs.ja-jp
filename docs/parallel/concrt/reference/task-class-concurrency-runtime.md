---
title: "task クラス (同時実行ランタイム) | Microsoft Docs"
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
  - "ppltasks/concurrency::task"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task クラス"
ms.assetid: cdc3a8c0-5cbe-45a0-b5d5-e9f81d94df1a
caps.latest.revision: 12
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# task クラス (同時実行ランタイム)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

並列パターン ライブラリ \(PPL\) `task` クラス。  `task` オブジェクトは、非同期的に、他のタスクと同時に実行できる処理、および同時実行ランタイムの並列アルゴリズムによって生成される並列処理を表します。  正常に終了した場合は、型 `_ResultType` の結果が生成されます。  型 `task<void>` のタスクでは結果が作成されません。  タスクは、他のタスクと関係なく待機および取り消しできます。  また、continuations\(`then`\)、および join\(`when_all`\) パターンと choice\(`when_any`\) パターンを使用して、他のタスクと共に構成することもできます。  
  
## 構文  
  
```  
template <  
   typename _Type  
>  
class task;  
  
template <>  
class task<void>;  
  
template<  
   typename _ReturnType  
>  
class task;  
```  
  
#### パラメーター  
 `_Type`  
 `T`  
 `_ReturnType`  
 このタスクの結果の型。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`result_type`|このクラスのオブジェクトによって生成される結果の型。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[task::task コンストラクター](../Topic/task::task%20Constructor.md)|オーバーロードされます。  `task` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[task::get メソッド](../Topic/task::get%20Method.md)|オーバーロードされます。  このタスクによって生成された結果を返します。  タスクが終了状態にない場合、`get` への呼び出しは、そのタスクが完了するまで待機します。  このメソッドは、`result_type` が `void` に指定されたタスクで呼び出された場合は値を返しません。|  
|[task::is\_apartment\_aware メソッド](../Topic/task::is_apartment_aware%20Method.md)|タスクが Windows ランタイム `IAsyncInfo` インターフェイスをラップ解除するか、こうしたタスクの子であるかを決定します。|  
|[task::is\_done メソッド \(同時実行ランタイム\)](../Topic/task::is_done%20Method%20\(Concurrency%20Runtime\).md)|タスクが完了したかどうかを決定します。|  
|[task::scheduler メソッド \(同時実行ランタイム\)](../Topic/task::scheduler%20Method%20\(Concurrency%20Runtime\).md)|このタスクのスケジューラを返します|  
|[task::then メソッド](../Topic/task::then%20Method.md)|オーバーロードされます。  継続タスクをこのタスクに追加します。|  
|[task::wait メソッド](../Topic/task::wait%20Method.md)|このタスクが終了状態になるまで待機します。  タスクの依存関係すべてが満たされ、バックグラウンド ワーカーによって実行用にまだ検出されていない場合、`wait` はタスクをインラインで実行できます。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[task::operator\!\= 演算子](../Topic/task::operator!=%20Operator.md)|オーバーロードされます。  2 つの `task` オブジェクトが異なる内部タスクを表すかどうかを決定します。|  
|[task::operator\= 演算子](../Topic/task::operator=%20Operator.md)|オーバーロードされます。  ある `task` オブジェクトの内容を別のオブジェクトの内容で置き換えます。|  
|[task::operator\=\= 演算子](../Topic/task::operator==%20Operator.md)|オーバーロードされます。  2 つの `task` オブジェクトが同じ内部タスクを表すかどうかを決定します。|  
  
## 解説  
 詳細については、「[タスクの並列化](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)」を参照してください。  
  
## 継承階層  
 `task`  
  
## 必要条件  
 **ヘッダー:** ppltasks.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)