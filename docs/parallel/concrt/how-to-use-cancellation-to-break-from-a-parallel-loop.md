---
title: "方法: キャンセル処理を使用して並列ループを中断する | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "並列検索アルゴリズム, 記述 [同時実行ランタイム]"
  - "記述 (並列検索アルゴリズムを) [同時実行ランタイム]"
ms.assetid: 421cd2de-f058-465f-b890-dd8fcc0df273
caps.latest.revision: 19
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: キャンセル処理を使用して並列ループを中断する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この例では、基本的な並列検索アルゴリズムを実装するためにキャンセルを使用する方法を示しています。  
  
## 使用例  
 次の例では、取り消し処理を使用して配列内の要素を検索します。  `parallel_find_any` 関数は [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) アルゴリズムと指定された値を含む位置を検索するために [concurrency::run\_with\_cancellation\_token](../Topic/run_with_cancellation_token%20Function.md) 関数を使用します。  並列ループでは値を見つけると、今後の作業をキャンセルするに [concurrency::cancellation\_token\_source::cancel](../Topic/cancellation_token_source::cancel%20Method.md) のメソッドを呼び出します。  
  
 [!code-cpp[concrt-parallel-array-search#1](../../parallel/concrt/codesnippet/CPP/how-to-use-cancellation-to-break-from-a-parallel-loop_1.cpp)]  
  
 [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) アルゴリズムは同時に処理を行います。  したがって、あらかじめ設定されている順序で操作を行うことはありません。  配列に値のインスタンスが複数含まれている場合、結果はそのいずれかの位置になります。  
  
## コードのコンパイル  
 プログラム例をコピーし、Visual Studio のプロジェクトに貼り付けるか、`並列配列search.cpp` という名前で、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行してファイルに貼り付けます。  
  
 **cl.exe \/EHsc parallel\-array\-search.cpp**  
  
## 参照  
 [キャンセル](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [並列アルゴリズム](../Topic/Parallel%20Algorithms.md)   
 [parallel\_for 関数](../Topic/parallel_for%20Function.md)   
 [cancellation\_token\_source クラス](../../parallel/concrt/reference/cancellation-token-source-class.md)