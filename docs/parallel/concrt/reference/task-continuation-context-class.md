---
title: "task_continuation_context クラス | Microsoft Docs"
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
  - "ppltasks/concurrency::task_continuation_context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_continuation_context クラス"
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
caps.latest.revision: 15
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# task_continuation_context クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`task_continuation_context` クラスを使用すると、継続する場所を指定できます。  このクラスは、Windows ストア アプリから使用する場合にのみ役に立ちます。  Windows ストア アプリを使用していない場合、タスク継続の実行コンテキストはランタイムによって決まり、構成できません。  
  
## 構文  
  
```  
class task_continuation_context : public details::_ContextCallback;  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[task\_continuation\_context::use\_arbitrary メソッド](../Topic/task_continuation_context::use_arbitrary%20Method.md)|タスクの継続コンテキストを作成します。このコンテキストを使用すると、ランタイムで継続用の実行コンテキストを選択できます。|  
|[task\_continuation\_context::use\_current メソッド](../Topic/task_continuation_context::use_current%20Method.md)|現在の実行コンテキストを表すタスクの継続コンテキスト オブジェクトを返します。|  
|[task\_continuation\_context::use\_default メソッド](../Topic/task_continuation_context::use_default%20Method.md)|タスクの既定の継続コンテキストを作成します。|  
  
## 継承階層  
 `_ContextCallback`  
  
 `task_continuation_context`  
  
## 必要条件  
 **ヘッダー:** ppltasks.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task Class](http://msdn.microsoft.com/ja-jp/5389e8a5-5038-40b6-844a-55e9b58ad35f)