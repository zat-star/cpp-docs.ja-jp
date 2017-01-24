---
title: "ループ | Microsoft Docs"
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
  - "loop_CPP"
  - "vc-pragma.loop"
dev_langs: 
  - "C++"
ms.assetid: 6d5bb428-cead-47e7-941d-7513bbb162c7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ループ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ループのコードを自動並列化によって処理する方法を制御します。また、ループを自動ベクター化の対象から除外します。  
  
## 構文  
  
```  
  
#pragma loop( hint_parallel(n) )  
```  
  
```  
  
#pragma loop( no_vector )  
```  
  
```  
  
#pragma loop( ivdep )  
```  
  
#### パラメーター  
 `hint_parallel(` `n` `)`  
 `n` 個のスレッドにまたがってこのループを並列化するようにコンパイラにヒントを与えます。ここで `n` は、正の整数リテラルまたはゼロです。  `n` がゼロの場合、スレッドの最大数が実行時に使用されます。  これはコンパイラに対するヒントであり、ループが並列化される保証はありません。  ループにデータ間の依存関係、つまり構造上の問題 \(たとえばループが、ループ本体を超えて使用されるスカラーに格納するなど\) がある場合、ループは並列化されません。  
  
 [\/Qpar](../Topic/-Qpar%20\(Auto-Parallelizer\).md) コンパイラ スイッチが指定されていない場合、このオプションはコンパイラによって無視されます。  
  
 `no_vector`  
 自動ベクター化は既定でオンになっており、必要と評価されたすべてのループのベクター化が試みられます。  このプラグマは、後続のループの自動ベクター化を無効にする場合に指定します。  
  
 `ivdep`  
 このループでベクターの依存関係を無視するようにコンパイラにヒントを与えます。  このプラグマは、`hint_parallel` と共に使用します。  
  
## 解説  
 `loop` プラグマを使用するには、ループ定義の中ではなく直前にプラグマを置きます。  プラグマは後続のループのスコープ内で有効です。  1 つのループに複数のプラグマを任意の順序で適用できますが、プラグマを 1 つずつ個別のステートメントで指定する必要があります。  
  
## 参照  
 [自動並行化と自動ベクター化](../parallel/auto-parallelization-and-auto-vectorization.md)   
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)