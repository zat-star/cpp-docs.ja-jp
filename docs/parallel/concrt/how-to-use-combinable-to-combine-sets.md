---
title: "方法: combinable を使用して集合を結合する | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "combinable クラス、例"
  - "結合 (combinable を使用してセットを) [同時実行ランタイム]"
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# 方法: combinable を使用して集合を結合する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここでは、[concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) クラスを使用して素数の集合を計算する方法について説明します。  
  
## 使用例  
 次の例では、素数の集合を 2 回計算します。  それぞれの計算結果は、[std::bitset](../Topic/bitset%20Class.md) オブジェクトに格納されます。  この例ではまず、集合を逐次的に計算した後で、並列処理によっても計算します。  また、それぞれの計算に要する時間もコンソールに出力します。  
  
 この例では、[concurrency::parallel\_for](../Topic/parallel_for%20Function.md) アルゴリズムおよび `combinable` オブジェクトを使用して、スレッド ローカルな集合を生成します。  次に、[concurrency::combinable::combine\_each](../Topic/combinable::combine_each%20Method.md) メソッドを使用して、スレッド ローカルな集合を結合し、最終的な集合として完成させます。  
  
 [!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-combine-sets_1.cpp)]  
  
 4 つのプロセッサを備えたコンピューターを使用したときのサンプル出力を次に示します。  
  
  **逐次時: 312 ミリ秒**  
**並列時: 78 ミリ秒**   
## コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、`parallel-combine-primes.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe \/EHsc parallel\-combine\-primes.cpp**  
  
## 参照  
 [並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)   
 [combinable クラス](../../parallel/concrt/reference/combinable-class.md)   
 [combinable::combine\_each メソッド](../Topic/combinable::combine_each%20Method.md)